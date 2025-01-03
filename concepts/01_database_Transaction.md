# 트랜잭션 (Transaction)

## 1. 트랜잭션의 개념

**트랜잭션**은 인가받지 않은 사용자로부터 데이터를 보장하기 위해 DBMS가 가져야 하는 특성입니다.
데이터베이스 시스템에서 하나의 논리적 기능을 정상적으로 수행하기 위한 작업의 기본 단위입니다.

## 2. 트랜잭션의 특성 (ACID)

### 2.1 원자성 (Atomicity)
- 트랜잭션을 구성하는 연산 전체가 모두 정상적으로 실행되거나 모두 취소되어야 하는 성질
- 트랜잭션의 연산 전체가 성공 또는 실패(All or Nothing)되어야 하는 성질

**주요 기법:**
- Commit/Rollback
- 회복성 보장

### 2.2 일관성 (Consistency)
- 시스템이 가지고 있는 고정요소는 트랜잭션 수행 전과 트랜잭션 수행 완료 후의 상태가 같아야 하는 성질

**주요 기법:**
- 무결성 제약조건
- 동시성 제어

### 2.3 격리성, 고립성 (Isolation)
- 동시에 실행되는 트랜잭션들이 서로 영향을 미치지 않아야 한다는 성질

**주요 기법:**
- 고립화수준(레벨 0, 1, 2, 3)

### 2.4 영속성 (Durability)
- 성공이 완료된 트랜잭션의 결과는 영속적으로 데이터베이스에 저장되어야 하는 성질

**주요 기법:**
- 회복기법

## 3. 트랜잭션의 상태

| 상태 | 설명 |
|------|------|
| **활동 상태 (Active)** | - 초기 상태<br>- 트랜잭션이 실행 중일 때 가지는 상태 |
| **부분 완료 상태 (Partially Committed)** | - 마지막 명령문이 실행된 후에 가지는 상태 |
| **완료 상태 (Committed)** | - 트랜잭션이 성공적으로 완료된 후 가지는 상태 |
| **실패 상태 (Failed)** | - 정상적인 실행이 더 이상 진행될 수 없을 때 가지는 상태 |
| **철회 상태 (Aborted)** | - 트랜잭션이 취소되고 데이터베이스가 트랜잭션 시작 전 상태로 환원된 상태 |

## 4. 트랜잭션 제어

### 4.1 트랜잭션 제어언어 (TCL)
트랜잭션 제어언어는 TCL(Transaction Control Language)이라고 하며, 트랜잭션의 결과를 허용하거나 취소하는 목적으로 사용되는 언어입니다.

### 4.2 TCL 명령어

| 명령어 | 설명 |
|--------|------|
| **COMMIT** | - 트랜잭션 확정<br>- 트랜잭션을 메모리에 영구적으로 저장 |
| **ROLLBACK** | - 트랜잭션 취소<br>- 트랜잭션 내역을 저장 무효화 |
| **CHECKPOINT** | - 저장 시기 설정<br>- ROLLBACK을 위한 시점을 지정 |

## 5. 병행 제어 (Concurrency Control)

### 5.1 병행 제어 개념
병행 제어는 다수 사용자 환경에서 여러 트랜잭션을 수행할 때, 데이터베이스 일관성 유지를 위해 상호 작용을 제어하는 기법입니다.

### 5.2 병행 제어의 목적
- 데이터베이스의 공유를 최대화
- 시스템의 활용도를 최대화
- 데이터베이스의 일관성을 유지
- 사용자에 대한 응답시간을 최소화

### 5.3 병행 제어 기법

#### 로킹 (Locking)
- 하나의 트랜잭션이 실행되는 동안 특정 데이터 항목에 대해 다른 트랜잭션이 동시에 접근하지 못하도록 상호배제(Mutual Exclusion) 기능을 제공
- 데이터베이스, 파일, 레코드 등은 로킹 단위가 될 수 있음
- 로킹 단위가 작아지면 데이터베이스 공유도가 증가하나 로킹 오버헤드도 증가

#### 낙관적 검증 (Optimistic Validation)
- 트랜잭션이 어떠한 검증도 수행하지 않고 일단 트랜잭션을 수행
- 트랜잭션 종료 시 검증을 수행하여 데이터베이스에 반영

#### 타임 스탬프 순서 (Time Stamp Ordering)
- 트랜잭션 실행 시작 전에 타임 스탬프를 부여
- 부여된 시간에 따라 트랜잭션 작업을 수행

#### 다중버전 동시성 제어 (MVCC)
- 트랜잭션의 타임 스탬프와 접근하려는 데이터의 타임 스탬프를 비교
- 직렬가능성이 보장되는 적절한 버전을 선택하여 접근

#### 2PC (2 Phase Commit)
- 분산 데이터베이스시스템에서 트랜잭션의 일관성을 유지하기 위한 기법
- 두 단계로 분리하여 제어:
  1. 준비 단계: 트랜잭션 수행 결과를 다른 분산 시스템에 알림
  2. 커밋 단계: 모든 분산 시스템에서 트랜잭션 수행 결과가 일치하는지 확인

## 6. 데이터베이스 고립화 수준 (Isolation Level)

### 6.1 고립화 수준 개념
고립화 수준은 다른 트랜잭션이 현재의 데이터에 대한 무결성을 해치지 않기 위해 잠금을 설정하는 정도입니다.

### 6.2 고립화 수준 종류

| 수준 | 설명 |
|------|------|
| **Read Uncommitted** | - 커밋되지 않은 데이터 읽기 허용<br>- 연산 중인 데이터에 대한 연산은 불허 |
| **Read Committed** | - 커밋된 데이터만 읽기 허용<br>- 연산이 완료된 데이터만 다른 트랜잭션이 읽기 가능 |
| **Repeatable Read** | - 선행 트랜잭션이 읽은 데이터는 종료 시까지 다른 트랜잭션이 갱신/삭제 불가 |
| **Serializable Read** | - 선행 트랜잭션이 읽는 데이터 영역에 대한 다른 트랜잭션의 접근을 제한 |

## 7. 회복 기법 (Recovery)

### 7.1 회복 기법 개념
회복 기법은 트랜잭션을 수행하는 도중 장애로 인해 손상된 데이터베이스를 손상되기 이전의 정상적인 상태로 복구시키는 작업입니다.

### 7.2 주요 회복 기법

#### REDO (재실행)
- 데이터베이스 비정상 종료 시 로그를 분석하여 완료된 트랜잭션 재작업
- 데이터베이스 손상 시 최근 복제본 적재 후 변경 내용 재실행

#### UNDO (취소)
- 완료되지 않은 트랜잭션의 변경 내용을 모두 취소
- 변경 내용의 신뢰성 상실 시 모든 변경 내용을 취소하여 복원

### 7.3 회복 기법 종류

#### 로그 기반 회복 기법
1. **지연 갱신 회복 기법 (Deferred Update)**
   - 트랜잭션 완료 전까지 데이터베이스에 기록하지 않음

2. **즉각 갱신 회복 기법 (Immediate Update)**
   - 트랜잭션 수행 중 갱신 결과를 바로 DB에 반영

#### 체크포인트 회복 기법 (Checkpoint Recovery)
- 검사점 이후 처리된 트랜잭션만 장애 발생 이전 상태로 복원

#### 그림자 페이징 회복 기법 (Shadow Paging Recovery)
- 트랜잭션 수행 시 복제본을 생성하여 장애 시 복구에 활용
