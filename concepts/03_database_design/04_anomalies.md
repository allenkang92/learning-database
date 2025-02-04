# 이상현상 (Database Anomalies)

## 1. 이상현상의 개념
- 데이터베이스 설계의 논리적 오류로 인한 데이터 불일치
- 정규화되지 않은 관계에서 발생하는 문제
- 데이터 무결성을 위협하는 현상

## 2. 이상현상의 종류

### 2.1 삽입 이상 (Insertion Anomaly)
- 데이터 삽입 시 발생하는 문제
- 불필요한 데이터 중복 발생
- 데이터 일관성 위협

### 2.2 삭제 이상 (Deletion Anomaly)
- 데이터 삭제 시 발생하는 문제
- 의도하지 않은 데이터 손실
- 참조 무결성 위반

### 2.3 갱신 이상 (Update Anomaly)
- 데이터 수정 시 발생하는 문제
- 부분 갱신으로 인한 불일치
- 데이터 일관성 훼손

## 3. 이상현상의 원인

### 3.1 부적절한 테이블 설계
- 잘못된 관계 설정
- 부적절한 키 설정
- 중복 데이터 존재

### 3.2 정규화 부족
- 함수적 종속성 문제
- 부분 종속성 존재
- 이행적 종속성 존재

## 4. 이상현상 해결 방안

### 4.1 정규화 적용
- 단계적 정규화 수행
- 함수적 종속성 분석
- 적절한 정규형 선택

### 4.2 테이블 재설계
- 관계 재정의
- 키 구조 개선
- 제약조건 추가

### 4.3 무결성 제약조건
- 참조 무결성 설정
- 도메인 제약조건
- 업무 규칙 반영

## 5. 이상현상 예방

### 5.1 설계 단계 검증
- 데이터 모델 검증
- 종속성 분석
- 무결성 검사

### 5.2 테스트 케이스 작성
- CRUD 연산 테스트
- 경계값 테스트
- 예외 상황 처리

## 6. 모니터링 및 유지보수

### 6.1 성능 모니터링
- 쿼리 실행 분석
- 데이터 변경 추적
- 이상현상 감지

### 6.2 지속적 개선
- 설계 개선사항 도출
- 성능 최적화
- 무결성 강화
