# Redis 데이터 조작하기
Redis에서 쿼리, 트리거 함수, 트랜잭션, 발행/구독을 포함한 데이터 조작 방법을 설명합니다.

Redis 운영에 필요한 다양한 측면들을 상세하게 정리했습니다.

## 주요 기능
- Redis 쿼리 엔진
- 프로그래밍 기능
- 트랜잭션
- 발행/구독 (Pub/Sub)

### Redis 쿼리 엔진
Redis 쿼리 엔진을 사용하면 키가 아닌 콘텐츠로 데이터를 검색할 수 있습니다. 해시와 JSON 객체의 필드를 유형에 따라 인덱싱하고 해당 필드에 대해 복잡한 쿼리를 수행할 수 있습니다. 예를 들어, 다음과 같은 검색이 가능합니다:

- 텍스트 필드의 일치 항목
- 지정된 범위 내의 숫자값
- 지정된 영역 내의 지리공간 좌표
- 텍스트 데이터에서 계산된 단어 임베딩에 대한 벡터 일치

### 프로그래밍 기능
Redis는 Lua 프로그래밍 언어를 위한 인터페이스를 제공하여 서버에서 스크립트를 저장하고 실행할 수 있습니다. 스크립트를 사용하면 서로 다른 클라이언트가 항상 동일한 로직으로 데이터를 업데이트하도록 보장할 수 있습니다. 또한 관련된 클라이언트 측 명령 시퀀스를 단일 서버 스크립트로 재구현하여 네트워크 트래픽을 줄일 수 있습니다.

### 트랜잭션
클라이언트는 종종 여러 데이터 객체에 관련된 변경을 수행하기 위해 일련의 명령을 실행합니다. 그러나 다른 클라이언트도 중간에 동일한 데이터 객체를 유사한 명령으로 수정할 수 있습니다. 이러한 상황은 데이터 손상이나 불일치를 초래할 수 있습니다.

트랜잭션을 사용하여 클라이언트의 여러 명령을 단일 단위로 그룹화할 수 있습니다. 트랜잭션의 명령은 다른 클라이언트의 명령 간섭 없이 순차적으로 실행됨을 보장합니다.

또한 WATCH 명령을 사용하여 트랜잭션 실행 직전에 사용된 키의 변경 사항을 확인할 수 있습니다. 트랜잭션을 구성하는 동안 감시 중인 데이터가 변경되면 실행이 안전하게 중단됩니다. 이 기능은 일반적으로 데이터가 한 번에 하나의 클라이언트에 의해서만 액세스되는 경우 효율적인 낙관적 동시성 제어를 위해 사용됩니다.

### 발행/구독
Redis는 동일한 이름의 잘 알려진 디자인 패턴을 구현하는 발행/구독(Pub/sub) 기능을 제공합니다. 특정 클라이언트 연결에서 서버가 관리하는 채널로 메시지를 발행할 수 있습니다. 해당 채널을 구독한 다른 연결은 보낸 순서대로 메시지를 수신합니다. 발행/구독을 사용하면 클라이언트 간에 소량의 데이터를 쉽고 효율적으로 공유할 수 있습니다.