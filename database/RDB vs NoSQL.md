# RDB vs NoSQL

## 1. RDB (Relational Database)
- **구조**: 테이블(행/열) 기반, 명확한 스키마 필요  
- **언어**: SQL 사용  
- **특징**:  
  - 데이터 무결성 보장 (ACID 지원)  
  - 스키마 기반으로 데이터 구조가 고정됨  
  - 조인(Join) 기능 지원  
  - 수직적 확장(Scale-Up)이 주로 사용됨  
- **예시**: MySQL, PostgreSQL, Oracle  

---

## 2. NoSQL (Not Only SQL)
- **구조**: 비정형 데이터 저장 가능, 스키마 유연  
- **언어**: DB별 전용 쿼리 언어 사용 (예: MongoDB는 BSON 기반 쿼리)  
- **특징**:  
  - 유연한 스키마 구조 (Schema-less)  
  - 수평적 확장(Scale-Out)에 유리  
  - BASE 모델 (Basically Available, Soft state, Eventually consistent)  
  - 고성능 읽기/쓰기, 대용량 처리에 적합  
- **종류 & 예시**:  
  - Key-Value: Redis  
  - Document: MongoDB  
  - Column: Cassandra, HBase  
  - Graph: Neo4j  

---

## 3. 비교 (RDB vs NoSQL)

| 구분 | RDB | NoSQL |
|------|-----|--------|
| **데이터 구조** | 정형 데이터 (테이블) | 비정형 데이터 가능 (JSON, KV 등) |
| **스키마** | 고정 스키마 | 유연한 스키마 |
| **확장성** | 수직 확장 (Scale-Up) | 수평 확장 (Scale-Out) |
| **트랜잭션** | ACID 보장 | BASE 모델 (궁극적 일관성) |
| **장점** | 무결성, 일관성, 복잡한 쿼리 지원 | 유연성, 확장성, 대규모 처리 |
| **단점** | 확장성 제약, 스키마 변경 어려움 | 조인 미지원, 일관성 약함 |
| **대표 사례** | MySQL, PostgreSQL | MongoDB, Redis, Cassandra |

---

## 4. 사용 사례
- **RDB**: 은행 거래, 주문/결제 시스템, ERP 등  
- **NoSQL**: 로그 수집, 캐시, SNS 피드, 실시간 분석, 빅데이터  
