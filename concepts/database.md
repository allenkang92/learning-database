데이터베이스의 개념

데이터베이스의 개요

자료와 정보

자료(Data) 

현실 세계로부터 단순한 관찰이나 측정을 통하여 수집된 사실이나 값

단순 데이터

무작위성

순수한 사실

수량, 문자 등

원시적인 형태

관찰, 측정 결과

단일 정보요소

정보(Information)

자료를 처리하여 얻은 결과로 의사결정을 하기 위한 값

의미가 있는 데이터

의미 있는 패턴 또는 규칙

가치 있는 인사이트

인지 가능한 판단

가공 및 구조화된 형태

해석, 예측, 추론

다양한 정보 요소

지식(Knowledge)

지식은 경험 또는 학습, 또는 자기성찰을 통해 얻은 사실, 진리, 정보에 대한 자각과 이해

정보 시스템

한 조직체의 데이터를 바탕으로 의사 결정에 필요한 정보를 추출하고 생성하는 시스템

사용 목적에 따라 인사 정보 시스템, 행정 정보 시스템 등으로 구분된다.

자료 처리 시스템의 종류

일괄 처리 시스템(Batch Processing System)

일괄 처리 시스템의 개념

일정 시간 동안 수집된 변동 자료를 컴퓨터의 입력 자료로 만들었다가 필요한 시점에 이 자료들을 입력하여 실행한 후 그 결과를 출력시켜 주는 방식의 시스템

대량의 데이터를 처리할 때 효율적

데이터를 처리하는 과정에서 중간 오류가 발생하면, 모든 데이터가 영향을 받을 수 있으므로 오류를 최소화하는 것이 중요

일괄 처리 시스템을 설계할 때는 오류 처리와 회복 기능을 반드시 고려

일괄 처리 시스템의 특징

그룹화

배치처리는 여러 개의 작업을 하나의 그룹으로 묶는다

작업은 일정한 순서 또는 우선순위에 따라 실행될 수 있다.

자동화

배치 처리는 사전에 정의된 절차에 따라 작업을 자동으로 수행한다.

인간의 개입이 필요 없이 지정된 작업을 자동으로 실행한다.

대량 처리

배치 처리는 대량의 데이터를 한 번에 처리할 수 있다.

대용량 데이터베이스에서 데이터 검증, 업데이트, 보고서 생성 등과 같은 작업을 효율적으로 수행할 수 있다.

비동기적 처리

배치 처리는 일반적으로 실시간 처리와 달리 비동기적으로 수행된다.

작업이 큐에 쌓여 순차적으로 처리되므로, 실시간 응답이 필요하지 않은 일괄적인 작업에 적합하다.

온라인 실시간 처리 시스템(Online Real Time Processing System)

온라인 실시간 처리 시스템의 개념

자료 발생 즉시 해당 자료를 처리하여 결과를 출력시켜주는 방식의 시스템

대화식 처리 방식

사용자가 입력한 요청을 즉시 처리하여 결과를 화면에 출력한다

실시간으로 처리되므로, 데이터의 정확성과 신뢰성이 매우 중요하다

데이터의 일관성과 무결성을 보장하기 위해 트랜잭션 처리 기능이 필수적

온라인 처리 시스템은 동시다발적인 사용자 요청을 처리할 수 있도록 시스템 자원을 효율적으로 관리해야 하므로 성능 최적화를 위한 캐싱, 인덱스, 파티셔닝 등의 기술이 적용되어야 한다.

온라인 실시간 처리 시스템의 특징

실시간 응답

사용자가 작업을 요청하면, 데이터베이스는 즉시 해당 작업을 처리하고 결과를 반환한다

상호 작용

사용자는 작업을 요청하고 결과를 확인한 후, 필요한 경우 추가적인 작업을 진행할 수 있다

동시성 처리

데이터베이스 시스템은 다중 사용자 환경에서 동시에 발생하는 요청을 효율적으로 처리하고 충돌을 방지하기 위한 동시성 제어 기법을 사용한다

실시간 데이터 업데이트

사용자가 데이터를 추가, 수정 또는 삭제하는 작업을 요청하면, 해당 변경 사항은 즉시 데이터베이스에 반영된다.

대화 형성

사용자와 데이터베이스 간의 대화를 통해 필요한 작업을 수행하고 결과를 확인하며, 필요한 경우 추가 작업을 진행할 수 있다.

분산 처리 시스템(Distributed Processing System)

물리적으로 분리된 각각의 데이터베이스를 네트워크로 연결하여 사용자들이 각 시스템이 하나인 것처럼 사용할 수 있도록 지원해주는 시스템

각각의 컴퓨터는 독립적으로 작업을 수행한다

대규모의 데이터를 처리할 때 유용하며, 데이터 처리 작업을 빠르고 효율적으로 수행할 수 있다.

데이터 처리 작업을 여러 대의 컴퓨터에서 병렬로 동시에 수행함으로써 빠른 처리 속도와 대규모 데이터 처리가 가능하다

여러 대의 컴퓨터에 분산 저장되어 있어서 데이터의 안전성과 보안성을 보장하기 위해 데이터의 복제, 분산 트랜잭션 처리, 보안 관리 등의 기술이 필요하다

클라우드 기반 처리(Cloud-based Processing)

클라우드 컴퓨팅 기술을 이용하여 데이터 처리를 수행하는 방식으로, 대량의 데이터를 처리할 때 사용한다.

인터넷 기반 처리(Internet-based Processing)

인터넷 기술을 이용하여 데이터 처리를 수행하는 방식으로, 대표적으로 웹 서버에서 동적인 페이지를 생성하는 웹 애플리케이션에서 사용된다.

데이터베이스의 정의

통합 데이터(Integrated Data)

각 사용자의 데이터를 한 곳에 모아 통합한 데이터

데이터는 여러 응용 프로그램에 의해 생성되고 유지보수 되기 때문에 각각의 데이터는 다른 형식과 구조로 되어 있어서 데이터베이스는 이러한 데이터를 일관된 형식과 구조로 통합하여 관리해야 한다.

저장 데이터(stored Data)

데이터베이스는 컴퓨터 하드웨어 저장 장치에 저장된 데이터

컴퓨터의 보조 기억 장치인 하드 디스크, 테이프 등에 저장되며, 데이터베이스 시스템에 의해 효율적으로 관리된다.

데이터베이스의 중요한 요소로서, 데이터베이스 시스템을 통해 데이터의 효율적인 관리와 보안이 보장되어야 한다.

운영 데이터(Operational Data)

데이터베이스는 어떤 조직의 고유 기능을 수행하기 위해 꼭 필요한 데이터

데이터베이스는 조직의 업무와 관련된 중요한 정보를 포함하고 있으므로, 데이터베이스 시스템을 통해 신속하고 정확한 데이터를 제공함으로서 조직의 의사 결정과 업무 수행을 지원한다

공용 데이터(Shared Data)

데이터베이스는 여러 사용자가 공동 소유, 관리, 활용하는 데이터.

데이터베이스의 특성 및 구성

데이터베이스의 특성

실시간 접근성

사용자의 수시적이고 비정형적인 질의에 대하여 실시간 처리로 응답할 수 있어야 한다.

사용자가 데이터베이스에 접근하여 데이터를 검색하거나 수정하는 등의 작업을 실시간으로 처리할 수 있는 능력을 의미한다.

주요 특성

실시간 응답

사용자가 데이터를 요청하면, 데이터베이스는 최신 정보를 검색하여 즉시 결과를 반환한다.

실시간 업데이트

데이터베이스에 저장된 데이터가 변경되면, 해당 변경 사항이 실시간으로 반영되어 사용자에게 최신 정보를 제공한다.

동시 접근

다수의 사용자가 동시에 데이터를 요청하고 처리할 수 있으며, 데이터베이스 시스템은 동시 접근을 조율하여 일관성과 무결성을 유지한다.

신속한 처리

사용자가 데이터를 요청하면, 데이터베이스는 최소한의 지연 시간으로 데이터를 검색하고 처리하여 결과를 제공한다

실시간 분석

데이터의 변경이 발생하면, 실시간으로 해당 데이터의 분석을 수행하고 결과를 제공한다

내용에 의한 참조

데이터베이스의 데이터는 그 주소나 위치에 의해 참조되는 것이 아니라 내용을 참조한다.

주요 특성

의미적 연결성

데이터베이스에서는 한 데이터가 다른 데이터를 참조함으로서 데이터 간의 관계를 정의하고 의미를 부여할 수 있어서 데이터 간의 상호 연결성을 유지하고 의미 있는 정보를 생성할 수 있다.

외래키

외래키는 다른 테이블이나 컬럼에서 데이터를 식별하는 역할을 하므로 외래키를 통해 데이터 간의 참조 관계를 구축할 수 있다.

데이터 무결성 유지

참조되는 데이터가 변경되거나 삭제되면, 이에 따라 참조하는 데이터에 대한 일관성을 유지하기 위해 적절한 제약 조건과 관계를 설정하여 데이터베이스에서 데이터의 일관성과 정확성을 유지할 수 있도록 한다.

관계형 데이터베이스

관계형 데이터베이스에서는 테이블 간의 관계를 정의하고 외래키를 사용하여 내용 참조를 구현하여 데이터베이스에서 데이터 간의 관계를 명확하게 표현하고 관리할 수 있다.

동시 공유

같은 내용의 데이터를 여러 사람이 동시에 공유할 수 있다.

주요 특성

동시성 제어

여러 사용자가 동시에 데이터를 읽고 쓸 수 있으므로, 동시성 제어 메커니즘을 통해 충돌을 방지하고 데이터의 일관성을 유지해야한디. 동시성 문제 ; 동시성 문제로는 경쟁 조건, 교착 상태, 일관성 유지 등이 있고, 이런 문제를 해결하기 위해 동시성 제어 메커니즘을 구현해야 한다.

동시 접근

각 사용자는 독립적으로 데이터를 조작하며, 다른 사용자의 작업과 상호 작용할 수 있어야 한다.

효율성

여러 사용자가 동시에 작업을 수행하므로 대기 시간이 줄어들고, 시스템의 활용도가 높아진다

계속적 변화

데이터베이스는 데이터의 삽입, 삭제, 갱신으로 내용이 계속 변한다

데이터베이스 시스템이 사용자의 요구사항에 맞게 데이터를 수정, 추가, 삭제하는 능력을 의미

주요 특성

유연한 구조

데이터베이스는 변경되는 요구사항에 따라 새로운 속성, 테이블, 관계 등을 추가하거나 기존 구조를 수정하여 적응할 수 있다.

데이터 마이그레이션

데이터베이스의 구조가 변경될 때 기존 데이터를 새로운 구조에 맞게 조정하는 작업을 의미한다

버전 관리

데이터베이스의 버전 관리를 통해 이전 버전과의 호환성을 유지하면서 새로운 버전을 도입할 수 있다.

확장성과 성능 개선

데이터베이스의 성능 향상을 위해 구조와 인덱스 등을 조정할 수 있어서 데이터베이스의 용량 증가, 사용량 변화, 쿼리 최적화 등에 따라 필요한 조치를 취하여 성능을 최적화할 수 있다.

지속적인 개선

사용자 요구사항의 변화나 기술의 진보에 따라 데이터베이스는 지속적으로 발전하고 개선된다.

데이터베이스 시스템의 구성

데이터베이스, DBMS, 데이터베이스 사용자, 스키마, 데이터베이스 언어

데이터베이스

자료와 정보를 저장하는 공간으로, 데이터베이스는 여러 개의 테이블로 구성되어 있다

테이블은 행과 열의 형태로 구성되어 있다

각 행은 레코드, 각 열은 속성이라고 한다

데이터베이스 관리 시스템

데이터베이스를 관리하고 제어하는 소프트웨어

DBMS는 데이터의 입력, 수정, 삭제 등을 처리하며, 데이터의 무결성, 일관성, 보안 등을 지원한다

Oracle, MySQL, PostgreSQL 등

데이터베이스 사용자

데이터베이스 관리자(DBA)

데이터베이스를 설계하고 구축하는 작업을 수행하기 위해 데이터 모델링, 테이블 생성, 인덱스 생성 등의 작업을 담당한다

DBMS를 관리한다

사용자 요구 정보 결정 및 데이터를 효율적으로 관리한다

백업 및 회복 전략을 정의한다.

행정적 책임을 가지고 있다

시스템 감시 및 성능을 분석한다

데이터 사전을 구성한다

데이터 접근 권한과 회복 절차를 수립한다

데이터베이스의 구성 요소 결정과 내장 저장 구조를 저으이 및 수정한다

데이터베이스의 성능을 최적화하는 작업 수행을 위해 SQL 튜닝, 인덱스 최적화, 파티셔닝 등의 작업을 담당한다

응용 프로그래머

데이터베이스를 기반으로 응용 프로그램을 개발하는 역할을 담당한다.

데이터베이스에 저장된 데이터를 조작하는 기능을 응용 프로그램에 구현한다

COBOL, PASCAL, C, Java 등의 개발 언어를 사용한다

업무: 요구사항 분석, 시스템 설계, 응용 프로그램 개발, 테스트 및 배포

일반 사용자

데이터베이스를 사용해 업무를 수행하는 사용자

데이터베이스에 저장된 데이터를 검색하거나, 데이터를 입력하거나, 데이터를 수정하거나, 데이터를 삭제하는 등의 작업을 수행한다

데이터베이스 언어

데이터 정의 언어(DDL)

데이터베이스의 구조와 스키마를 정의하는 데 사용

데이터 조작 언어(DML)

데이터베이스에 저장된 데이터를 검색, 삽입, 수정, 삭제하는 데 사용

데이터 제어 언어(DCL)

데이터베이스에 접근하고 사용자의 권한을 관리하는 데 사용