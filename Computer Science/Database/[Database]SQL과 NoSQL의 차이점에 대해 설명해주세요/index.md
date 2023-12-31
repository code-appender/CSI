> SQL : 관계형 DB <br>
> NoSQL : 비관계형 DB

## SQL

- RDBMS에서 데이터를 저장, 수정, 삭제, 검색할 수 있음
- 정해진 데이터 스키마에 따라 테이블에 저장
  - 각 테이블마다 명확하게 정의된 구조가 있음. → 해당 구조는 필드의 이름, 데이터 유형으로 정의됨. 
- 데이터의 중복을 피하기 위해 관계를 통해 여러 테이블에 분산
- 하나의 테이블에서 중복 없이 하나의 데이터만을 관리하기 때문에 다른 테이블에서 부정확한 데이터를 다룰 위험이 없어짐.
- 일반적으로 수직적 확장만 지원.
  - 수직적 확장 : 단순히 DB 서버의 성능을 향상시키는 것 (ex. CPU 업글)
- 장점
  - 명확하게 정의된 스키마, 데이터 무결성 보장
  - 관계는 각 데이터를 중복없이 한번만 저장
- 단점
  - 덜 유연. 데이터 스키마를 사전에 잘 설계해야함
  - 조인문이 많은 복잡한 쿼리가 생길 수 있음
  - 대체로 수직적 확장만 가능

## NoSQL

- NoSQL에서는 레코드를 문서(Documents)라고 부름.
    - 문서는 Json과 비슷한 형태로 저장.
- RDBMS처럼 여러 테이블에 저장하지 않고 관련 데이터를 동일한 **컬렉션**에 저장.
- 즉, 조인할 필요없이 필요한 모든 것을 갖춘 문서를 작성하는 것이 NoSQL
- 수평적 확장 가능.
    - 더 많은 서버 추가, DB가 전체적으로 분산됨을 의미 (하나의 DB에서 작동하지만 여러 호스트에서 작동)
- 장점
    - 스키마가 없기때문에 유연. 언제든지 데이터를 조정, 새로운 필드 추가 가능
    - 애플리케이션이 필요로 하는 형식으로 저장됨. → 읽기 속도가 빨라짐.
    - 수직, 수평 확장이 가능 → 애플리케이션이 발생시키는 모든 요청 처리 가능
- 단점
    - 유연성으로 인해 데이터 구조 결정을 미루게 될 수 있음.
    - 데이터 중복을 계속 업데이트해야함
    - 여러 컬렉션에 데이터가 중복되어 있기 때문에 수정 시 모든 컬렉션에서 수정해야함. 

### 차이점 요약
    1. SQL은 관계형, NoSQL은 비관계형
    2. SQL은 구조화된 언어를 사용, 사전 정의된 스키마가 존재. NoSQL은 비정형 데이터에 대한 동적 스키마가 존재.
    3. SQL은 수직적 확장이 가능, NoSQL은 수평적 확장이 가능.
    4. SQL은 테이블 기반, NoSQL은 문서, key-value, 그래프 또는 wide-column store
    5. SQL은 다중 행 트랜잭션에 효과적, NoSQL은 JSON 같은 비정형 데이터에 효과적.

#### 참고/출처
[SQL과 NOSQL의 차이](https://gyoogle.dev/blog/computer-science/data-base/SQL%20&%20NOSQL.html)<br>
[SQL과 NoSQL 비교](https://www.integrate.io/ko/blog/sql-vs-nosql-5-critical-differences-ko/)