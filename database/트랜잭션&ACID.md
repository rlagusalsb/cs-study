# 트랜잭션 & ACID

## 핵심 요약

* **트랜잭션**: 데이터베이스에서 하나의 논리적 작업 단위 (모두 성공 또는 모두 실패)
* **ACID**: 트랜잭션이 지켜야 할 4가지 성질
  - **Atomicity (원자성)**: 전부 실행되거나 전부 취소
  - **Consistency (일관성)**: 무결성 제약 조건 항상 만족
  - **Isolation (격리성)**: 동시에 실행 시 서로 간섭하지 않음
  - **Durability (지속성)**: 커밋된 결과는 영구적으로 보장

---

## 상세 설명

### 1. 트랜잭션 (Transaction)

* 데이터베이스에서 **논리적 작업 단위**
* 은행 계좌 이체 예시: A에서 출금, B에 입금 → 둘 다 성공하거나 둘 다 실패해야 함
* 주요 제어 명령어:
  - `BEGIN` / `START TRANSACTION`
  - `COMMIT`: 트랜잭션 결과 영구 반영
  - `ROLLBACK`: 실행 내용 취소

---

### 2. ACID 특성

1. **Atomicity (원자성)**  
   - 트랜잭션은 쪼갤 수 없는 최소 단위  
   - 일부만 실행되는 일 없음  

2. **Consistency (일관성)**  
   - 트랜잭션 실행 전후 데이터 무결성 유지  
   - 제약조건(Unique, FK 등) 위배되지 않음  

3. **Isolation (격리성)**  
   - 동시에 실행되는 트랜잭션 간 간섭 방지  
   - 격리 수준(Isolation Level) 존재  
     * Read Uncommitted → Dirty Read 발생 가능  
     * Read Committed → Non-repeatable Read 발생 가능  
     * Repeatable Read → Phantom Read 발생 가능  
     * Serializable → 완벽한 격리, 성능 저하 가능  

4. **Durability (지속성)**  
   - 트랜잭션 커밋 후 결과는 DB에 영구 저장  
   - 장애 발생 시에도 보장 (로그, 복구 메커니즘 활용)

---

### 3. 트랜잭션에서 발생 가능한 문제

* **Dirty Read**: 커밋되지 않은 데이터를 읽음  
* **Non-repeatable Read**: 같은 쿼리 반복 시 결과 달라짐  
* **Phantom Read**: 같은 조건 조회 시 새로운 행이 나타남  

---
