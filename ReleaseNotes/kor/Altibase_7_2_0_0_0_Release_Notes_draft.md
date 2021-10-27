<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Altibase 7.2.0.0.1 Release Notes](#altibase-72001-release-notes)
  - [시스템 요구사항](#%EC%8B%9C%EC%8A%A4%ED%85%9C-%EC%9A%94%EA%B5%AC%EC%82%AC%ED%95%AD)
    - [하드웨어 최저 사양](#%ED%95%98%EB%93%9C%EC%9B%A8%EC%96%B4-%EC%B5%9C%EC%A0%80-%EC%82%AC%EC%96%91)
    - [운영 체제 및 플랫폼](#%EC%9A%B4%EC%98%81-%EC%B2%B4%EC%A0%9C-%EB%B0%8F-%ED%94%8C%EB%9E%AB%ED%8F%BC)
  - [새로운 기능](#%EC%83%88%EB%A1%9C%EC%9A%B4-%EA%B8%B0%EB%8A%A5)
    - [**JDBC** **API Specification 4.2** 부분 지원 (PROJ-2707)](#jdbc-api-specification-42-%EB%B6%80%EB%B6%84-%EC%A7%80%EC%9B%90-proj-2707)
    - [altiComp 커밋 카운트 설정 기능 추가](#alticomp-%EC%BB%A4%EB%B0%8B-%EC%B9%B4%EC%9A%B4%ED%8A%B8-%EC%84%A4%EC%A0%95-%EA%B8%B0%EB%8A%A5-%EC%B6%94%EA%B0%80)
    - [CREATE QUEUE 및 ALTER QUEUE 구문에 DELETE 절 추가](#create-queue-%EB%B0%8F-alter-queue-%EA%B5%AC%EB%AC%B8%EC%97%90-delete-%EC%A0%88-%EC%B6%94%EA%B0%80)
    - [APRE SQL_NUMERIC_STRUCT 배열 처리 기능 추가 ?](#apre-sql_numeric_struct-%EB%B0%B0%EC%97%B4-%EC%B2%98%EB%A6%AC-%EA%B8%B0%EB%8A%A5-%EC%B6%94%EA%B0%80-)
    - [범위 파티션드 객체에 파티션 추가 연산 추가](#%EB%B2%94%EC%9C%84-%ED%8C%8C%ED%8B%B0%EC%85%98%EB%93%9C-%EA%B0%9D%EC%B2%B4%EC%97%90-%ED%8C%8C%ED%8B%B0%EC%85%98-%EC%B6%94%EA%B0%80-%EC%97%B0%EC%82%B0-%EC%B6%94%EA%B0%80)
  - [성능 및 안정성 향상](#%EC%84%B1%EB%8A%A5-%EB%B0%8F-%EC%95%88%EC%A0%95%EC%84%B1-%ED%96%A5%EC%83%81)
    - [OLTP Scalability 성능 향상(TASK-7073)](#oltp-scalability-%EC%84%B1%EB%8A%A5-%ED%96%A5%EC%83%81task-7073)
    - [언두 테이블스페이스 재사용 안정성 향상](#%EC%96%B8%EB%91%90-%ED%85%8C%EC%9D%B4%EB%B8%94%EC%8A%A4%ED%8E%98%EC%9D%B4%EC%8A%A4-%EC%9E%AC%EC%82%AC%EC%9A%A9-%EC%95%88%EC%A0%95%EC%84%B1-%ED%96%A5%EC%83%81)
    - [PARTITIONED TABLE에 대한 LIMIT FOR UPDATE 성능 개선](#partitioned-table%EC%97%90-%EB%8C%80%ED%95%9C-limit-for-update-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0)
    - [트랜잭션 로그 기록 성능 향상(TASK-6983)](#%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-%EB%A1%9C%EA%B7%B8-%EA%B8%B0%EB%A1%9D-%EC%84%B1%EB%8A%A5-%ED%96%A5%EC%83%81task-6983)
    - [서브쿼리의 인라인 뷰에 ORDER BY절 사용 시 SQL 성능 개선](#%EC%84%9C%EB%B8%8C%EC%BF%BC%EB%A6%AC%EC%9D%98-%EC%9D%B8%EB%9D%BC%EC%9D%B8-%EB%B7%B0%EC%97%90-order-by%EC%A0%88-%EC%82%AC%EC%9A%A9-%EC%8B%9C-sql-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0)
    - [2.2 변경 사항](#22-%EB%B3%80%EA%B2%BD-%EC%82%AC%ED%95%AD)
    - [2.3 패키지](#23-%ED%8C%A8%ED%82%A4%EC%A7%80)
    - [2.4 다운로드](#24-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

Altibase 7.2.0.0.1 Release Notes
===============================

## 시스템 요구사항

### 하드웨어 최저 사양

* 1GB RAM (권장: 2GB)
* 1 CPU (권장: 2 CPUs)
* 4GB 하드 디스크 여유 공간 (권장: 12GB)

### 운영 체제 및 플랫폼

Altibase 7.2.0.0.1 는 아래 표에 나열된 운영체제와 플랫폼 상에서 운영 가능하다.

| OS    | CPU    | 리눅스 배포판 버전                                           | CPU 비트 수 | 시스템 요구사항                                              |
| ----- | ------ | ------------------------------------------------------------ | :---------: | :----------------------------------------------------------- |
| LINUX | x86-64 | Red Hat Enterprise Linux 6<br />Red Hat Enterprise Linux 7<br />Red Hat Enterprise Linux 8 |   64-bit    | - GNU glibc 2.12 이상<br />- Altibase JDBC Driver : JRE 1.8 이상 |

> Altibase 서버/클라이언트 모두 64-bit 만 지원한다.
>
> Red Hat Enterprise Linux 6, 7, 8 마이너 버전에 대해 호환성을 보장한다.

#### 릴리스 정보

## 새로운 기능

### **JDBC** **API Specification 4.2** 부분 지원 (PROJ-2707)

JDBC API Specification 4.2 지원으로 인한 변경 사항은 여기에서 확인하라.

- **Auto-loading of JDBC driver class**

  명시적으로 Class.forName() 클래스를 로딩할 필요없이 META-INF/services/java.sql.Driver 파일을 이용한 자동 드라이버 로딩 기능 지원

- **Wrapper Pattern Support**

  프록시에서 구현 객체에 대한 참조를 얻는 JDBC 4.0 표준 인터페이스를 지원한다. 커넥션풀 등에서 생성하는 프록시 객체에서 JDBC 객체를 획득할 수 있다.

  ```java
  try (Connection sWrappedCon = dbPool.getConnection()) {
      if (sWrappedCon.isWrapperFor(AltibaseConnection.class)) {
          AltibaseConnection connection = sWrappedCon.unwrap(AltibaseConnection.class);
          ...
          ...
  }
  ```

- **National Character Set Support**

  JDBC 4.0 스펙인 표준 다국어 처리 인터페이스 지원

- **Aborting Connections**

  비동기적으로 데이터베이스와의 물리적 연결을 종료하는 Connection.abort() 인터페이스 지원

- **Standard Socket Network Timeout API Support**

  데이터베이스 서버로부터 소켓 응답 대기 시간을 설정하는 표준 인퍼페이스Connection.setNetworkTimeout() 지원

- **Connection Management Enhancements**

  Validation Query없이 Connection 객체에서 유효성 검사를 수행하는 Connection.isValid() 지원

- **Large Update Counts Support**

  대용량 레코드 업데이트를 위한 executeLargeUpdate(), executeLargeBatch() 지원

- **Set Client Information Support**

  Connection.setClientInfo()를 이용한 클라이언트 어플리케이션 속성(name) 설정 지원

- **java.sql.SQLType interface Support**

  JDBC 4.2 표준 인터페이스 java.sql.SQLType을 구현한 AltibaseJDBCType 지원

### altiComp 커밋 카운트 설정 기능 추가

커밋(commit) 카운트를 설정할 수 있는 프로퍼티 COUNT_TO_COMMIT가 추가되었다. 관련 내용은 [Altibase 7.2 Utilities Manual](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_7.2/kor/Utilities.md#count_to_commit) 에서 확인할 수 있다.

### CREATE QUEUE 및 ALTER QUEUE 구문에 DELETE 절 추가

큐(QUEUE) 테이블에 DELETE 문 허용 여부를 설정하는 DELETE 절이 추가되었다.

DELETE OFF로 DELETE 문을 허용하지 않으면 DELETE 문을 허용한 경우보다 DEQUEUE 병렬 수행 성능이 향상된다. 구문 사용 방법은 [Altibase 7.2 SQL Reference 매뉴얼](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_7.2/kor/SQL1.md#create-queue) 을 참고한다. 관련하여 성능 뷰 [V$QUEUE_DELETE_OFF](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_7.2/kor/GeneralReference_4.md#vqueue_delete_off)가 추가되었다. 

### APRE SQL_NUMERIC_STRUCT 배열 처리 기능 추가 ?

### 범위 파티션드 객체에 파티션 추가 연산 추가

범위 파티셔드 테이블에 파티션 추가(ADD PARTITION) 구문을 지원한다. 이 기능 추가로 기본 파티션 없는 범위 파티션드 테이블 생성이 가능하다. 

**Altibase 7.2 에서 범위 파티션드 테이블 생성 시 주의 사항**

- Altibase 7.2 에서는 기본 파티션이 없는 범위 파티션드 테이블을 생성할 수 있다. 

  참고로 기본 파티션이 없는 범위 파티션드 테이블을 생성하면 SYS_TABLE_PARTITIONS_에서 PARTITION_NAME 이 없는 파티션이 추가로 생성된다. 

- 범위 파티션드 객체에서 파티션 추가는 기본 파티션이 없는 범위 파티션드 테이블에서만 사용할 수 있다.

- 기본 파티션이 없는 범위 파티션드 테이블은 기본 파티션 추가 연산을 수행할 수 없다.

- 기본 파티션이 있는 범위 파티션드 테이블은 기본 파티션 삭제 연산을 수행할 수 없다.

- 기본 파티션이 없는 범위 파티션드 테이블은 파티션 키로 널(NULL) 값을 사용할 수 없다.

- 기본 파티션이 없는 범위 파티션드 테이블은 CONJOIN/DISJOIN 구문을 사용할 수 없다.

- 범위 파티션드 테이블이 이중화 대상 테이블인 경우 파티션 추가 연산을 수행할 수 없다.

  

## 성능 및 안정성 향상

### OLTP Scalability 성능 향상(TASK-7073)

- Linux x86-64 CPU 코어 수 24코어 이상에서 조회 트랜잭션 성능 저하 현상 개선

- 로깅 구조를 개선하여 메모리 DB 삭제(DELETE) 트랜잭션 성능 향상

- In-place MVCC 동작 방식을 개선하여 디스크 DB 변경 트랜잭션 성능 향상

- 테이블 잠금(TABLE LOCK) 병목 개선

- INSERT/UPDATE 트랜잭션 처리 시 불필요한 트랜잭션 로그 기록을 제거하여 성능 향상

- 온라인 로그파일 압축 시 메모리 할당/해제 병목 개선
  - Altibase 운용 중 기본 메모리 사용이 증가합니다. 
    V$MEMSTAT의 Storage_Memory_Recovery 항목으로 이전 버전과 증가량을 확인할 수 있습니다. 
    메모리 증가량은 TRANSACTION_TABLE_SIZE에 영향을 받습니다. TRANSACTION_TABLE_SIZE 기본값 1024 경우 약 32MB 증가, 최대값 16384 경우 약 500M 증가합니다. 

    

- Volatile DB 트랜잭션 성능 향상

- 커밋 병목 및 가비지 콜렉션 쓰레드 병목 개선

  - 트랜잭션 커밋 후 테이블 정보 업데이트 병목 개선

- Memory DB 트랜잭션 성능 향상
  - 디스크 읽기를 유발하는 함수의 병목을 제거하여 성능 향상
  - Group Commit Log 기능 추가

### 언두 테이블스페이스 재사용 안정성 향상

디스크 인덱스와 언두 테이블스페이스의 불필요한 관계를 제거하여 버그 발생 위험 요소 제거하였다. 디스크 페이지 공간 효율 개선으로 관련 프로퍼티들의 기본값 및 최대값이 변경되었다. 

- INDEX_INITTRANS 최대값이 30에서 50으로 변경
- INDEX_MAXTRANS 기본값과 최대값이 30에서 50으로 변경

### PARTITIONED TABLE에 대한 LIMIT FOR UPDATE 성능 개선

### 트랜잭션 로그 기록 성능 향상(TASK-6983)

### 서브쿼리의 인라인 뷰에 ORDER BY절 사용 시 SQL 성능 개선

조걸절(WHERE 또는 HAVING 절)에서 사용한 서브쿼리의 인라인 뷰에 ORDER BY절을 사용한 SQL에서 특정 조건을 만족하는 경우 불필요한 SORT 작업을 제거하여 성능 향상

- SQL 사용 예

  ```sql
  SELECT *
    FROM T1
   WHERE I1 IN (SELECT /*+ NO_UNNEST */I1
                  FROM (SELECT *
                          FROM T2
                         ORDER BY I2, I3));
  ```

이 영향을 받는 SQL은 실행 계획이 SUBQUERY FILTER 안에 SORT 플랜 노드 없어진다.

- #### Scalar subquery 성능 개선

  Scalar subquery의 결과가 단일 레코드인지 확인하는 과정에서 발생하는 오버헤드 제거하여 access cost를 줄임

- #### 트랜잭션 로그 기록 성능 향상(TASK-6983)

  로그 압축 알고리즘을 압축 속도가 빠른 LZ4 로 변경하였다.

- #### 휘발성/비휘발성 메모리 DB 트랜잭션 성능 향상

  메모리 테이블 객체 식별자 추적 단계를 간소화하여 휘발성/비휘발성 메모리 DB 트랜잭션 성능 향상

- #### 이중화 성능 향상

  - 압축 로그에서 이중화에 필요한 로그만 압축 해제하는 기능 추가하여 이중화 Sender 성능 향상
  - xLog 압축 알고리즘을 LZO에서 LZ4로 변경하여 압축 성능 향상

#### 2.1.3 기능 개선

##### 2.1.3.1 SQL 확장

###### ~~anonymous block -매뉴얼 없음(PROJ-2708)~~ (7.1 반영되었음. 7.1.0.2.3)

###### ~~C/C++ External Procedure의 internal mode procedure 지원 (PROJ-2717)~~ 7.1에 이미 반영. 7.1.0.3.3

External procedure는 external procedure agent process를 통해서 외부 library를 load하고, server process와 external procedure agent간의 통신을 통해서 외부 함수를 호출합니다. Internal mode procedure는 외부 library를 server process가 직접 load하고, 외부 함수를 직접 호출하여 external procedure에 비해서 빠르게 동작합니다.

###### ~~multiple table update, delete~~ (trunk에만 반영. 7.2에 반영되지 않음 : BUG-47432)

multiple update, delete 구문을 지원합니다. 자세한 내용은 SQL 매뉴얼- [multiple_delete](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/SQL3.md#delete) , [multiple_update](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/SQL3.md#update) 을 참고하시기 바랍니다.

###### ~~memory partition simple query (PROJ-2705)~~ trunk에만 반영. 7.2에 반영되지 않음

기존에는 memory table에 대해서만 simple query 최적화를 지원하였으나, memory partition table 의 경우도 지원하도록 수정하였습니다.

###### ~~fetch across rollback (PROJ-2694)~~ 6.5.1.5.0, 7.1.0.1.3 에 이미 반영

CURSOR HOLD ON 기능을 이용하여 rollback 할 때, Fetch out of sequence 에러가 발생하는 문제를 해결하기 위하여 fetch across rollback 기능을 제공합니다.

###### ~~계층형 쿼리(Hierarchy Query) 조인 지원 (PROJ-2509)~~ trunk에만 반영

###### ~~RANGE_USING_HASH partition 지원~~ 7.1에 이미 반영 (7.1.0.1.4)

파티션드 객체에 RANGE_USING_HASH PARTITION 이 추가되었습니다. 해시를 사용한 범위 파티셔닝(RANGE_USING_HASH PARTITION)은 해당 해시(hash) 값을 기준으로 범위(range)를 정해서 분할하는 방법입니다.

##### 2.1.3.2 Spatial SQL 개선

###### ~~SRID(Spatial Reference Identifier) interface 지원~~ (PROJ-2422) 7.1 에 이미 반영. 7.1.0.4.0

###### GEOMETRY 데이터타입 표현방법 추가

- EWKT(Extended Well-Known Text) 형식: WKT 형식에 공간 객체를 표현하는 SRID(Spatial Reference Identifier) 정보가 추가된 것이다.
- EWKB(Extended Well-Known Binary) 형식: WKB 형식에 공간 객체를 표현하는 SRID(Spatial Reference Identifier) 정보가 추가된 것이다

###### 공간 함수

SRID 지원에 따라, 아래의 공간함수가 추가되었다.

* ASEWKT
* ASEWKB
* SRID
* SETSRID
* GEOMFROMEWKT 
* GEOMFROMEWKB
* ACSGetGeometrySRID
* ST_Collect
* ST_IsCollection
* ST_LinestringFromWKB
* ST_MakeEnvelope
* ST_MakeLine
* ST_MakePoint
* ST_Point
* ST_PolygonFromText
* ST_Transform

##### 2.1.3.3 이중화 기능개선

###### ~~이중화 대상 테이블에 DDL 복제 기능 추가(PROJ-2677)~~ 7.1에 이미 반영. 7.1.0.1.4

이중화를 통하여 DDL 동기화(Synchronization)를 허용합니다. 이 기능을 사용하기 위해서는 각노드의 REPLICATION_DDL_SYNC 프로퍼티를 1로 설정해야 합니다. 또한, 각 노드의 [REPLICATION_DDL_ENABLE](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_2.md#replication_ddl_enable) 프로퍼티를 1로 설정하고, [REPLICATION_DDL_ENABLE_LEVEL](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_2.md#replication_ddl_enable_level)이 동일해야 합니다.

DDL 동기화를 사용하기 위해 다음의 제약 조건을 따릅니다.

- DDL 동기화를 수행할 노드들의 이중화가 동작하고 있어야 한다.

-  DDL 동기화를 수행할 Local 노드와 Remote 노드의 Table 이름이 같아야 한다.
-  DDL 동기화를 수행할 Local 노드와 Remote 노드의 Table 파티션이름이 같아야 한다.
-  DDL 동기화를 수행할 이중화 대상 유저의 이름이 같아야 한다.
-  한번에 하나의 노드에서만 DDL 동기화를 수행해야 한다.
-  DDL 동기화를 수행할 각 이중화 노드의 REPLICATION_DDL_ENABLE과 REPLICATION_DDL_ENABLE_LEVEL 프로퍼티 값이 같아야 한다.
-  Altibase Patch 버전(5자리)이 동일해야한다.

Propagation 옵션 사용시 DDL 동기화를 허용하지 않는다.

##### 2.1.3.4 응용 프로그램 개발 인터페이스 확장 및 개선

###### CLI에서 SQL_NUMERIC_STRUCT 데이터 타입 지원 및 배열처리 지원

###### JDBC 연결속성 lob_null_select

Lob 컬럼값이 null인 경우, ResultSet.getBlob() 및 ResultSet.getClob() 수행시 NULL을 반환할수 있도록 JDBC 연결 속성 lob_null_select가 추가되었습니다. 기본값은 off로, 이 경우 반환되는 NULL 에 대한 예외처리를 해야 합니다.

###### JDBC fetch 성능 개선

##### 2.1.3.5 내장 패키지 및 함수

###### DBMS_STANDARD 패키지 - 매뉴얼없음

DBMS_STANDARD 패키지를 통해서 trigger event를 확인하는 함수를 제공

###### DBMS_METADATA 패키지 제공

DBMS_METADATA 패키지는 데이터베이스 딕셔너리로부터 객체 생성 DDL 구문 또는 권한 GRANT 구문을 추출하는 기능을 제공한다. 

###### DBMS_SQL_PLAN_CACHE 패키지 제공 - 매뉴얼없음

SQL PLAN CACHE에 PLAN을 keep/unkeep 할 수 있는 기능이 추가되었습니다.

###### DBMS_OUTPUT 패키지에 print_enable/print_disable 프로시저 추가

PSM내에서 println 기능을 enable, disable 할수 있는 기능을 제공합니다. 세션단위로 수행됩니다.

###### DBMS_SHARD 패키지

###### DBMS_SHARD_GET_DIAGNOSTICS 패키지

###### DBMS_LOCK 패키지에 sleep2 프로시저 추가

micro second sleep 을 지원하는 시스템 저장 프로시저 sleep2가 추가되었습니다.

###### SYS_SPATIAL 패키지

###### UTL_COPYSWAP 패키지 

UTL_COPYSWAP 패키지는 테이블 스키마 복사, 데이터 복제, 테이블 교환 인터페이스를 제공한다.

###### UTL_SHARD_ONLINE_REBUILD 패키지

##### 2.1.3.6 클라이언트 툴

###### Shard Manager 3.x? 지원

Shard Manager는 Altibase Sharding의 데이터 노드와 샤드 객체에 대한 구성 및
관리를 돕는 도구이다. Altibase Sharding은 다수의 데이터베이스로 구성되기 때문에,
각 데이터베이스와 객체를 관리하는 데에 많은 비용이 들 수 있다. 이런 환경에서,
사용자는 Shard Manager를 사용하여 업무 효율성을 향상시킬 수 있다

###### AWRITE 유틸리티

로그 파일을 생성할때 사용되는 시스템콜을 결정하기 위해 시스템콜의 응답시간을 출력하는 awrite 유틸리티를 추가합니다.

###### DUMPTRC 의 -x 옵션

altibase 실행파일의 버전과 dumptrc의 버전이 다른 경우에도 콜스택을 출력할 수 있도록 옵션이 추가되었다.

###### AIX 7, Power Linux LE(Little endian)에서 altimon 지원

AIX 7.x 버전 및 Power Linux LE 에서도 altimon을 사용할 수 있다.

###### iLoader 환경변수 ILO_FILE_PERMISSION 추가

iloader가 생성하는 파일 권한을 설정하는 환경 변수이다. 값을 설정하지 않으면 666 ( user:rw, group:rw, other: rw)로 설정된다.

###### iLoader 의 -stmt_prefix 옵션 추가

iloader로 특정 샤드 노드에 데이터를 in/out하기 위한 옵션으로 -stmt_prefix 가 추가되었습니다. 자세한 내용은 [iLoader User's Manual -일반옵션](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/iLoader.md#일반-옵션) 을 참고하시기 바랍니다.

###### iLoader의 -extra_col_delimiter 옵션 추가

레코드 마지막 컬럼 뒤에 컬럼 구분자와 레코드 구분자가 연달아 위치한 경우, 이를 레코드의 끝으로 인식하기 위한 옵션이다.

###### iLoader의 -geom 옵션 추가

out 모드 수행시, 공간 데이터를 Well-Known Binary (WKB) 포맷으로 out 하기 위한 옵션이다.

###### aexport  환경변수 AEXPORT_FILE_PERMISSION 추가

aexport가 생성하는 파일 권한을 설정하는 환경 변수이다. 값을 설정하지 않으면 666 ( user:rw,  group:rw,  other: rw)로 설정된다.

#### 2.1.4 효율성

##### 2.1.4.1 서버 성능 향상

###### TABLE LOCK 병목구간 개선

TABLE LOCK 관리자 타입에서 Spin lock 모드가 제거 되고, light Mutex 모드가 추가되었다.

###### TABLESPACE_MANAGER_MUTEX 병목 제거 

###### 디스크 temp table 성능 개선

###### SERIAL FILTER 의 적용으로 쿼리 수행 성능을 개선

SERIAL_FILTER 힌트 및 SERIAL_EXECUTE_MODE 프로퍼티가 추가되었다. 실행계획에서 FILTER SERIAL EXECUTE 를 확인할 수 있다.

###### DEQUEUE 병렬 수행시 성능 개선

병렬로 DEQUEUE 수행 시 발생하는 병목을 제거하여 성능을 개선합니다.

###### 서버 시작시, 버퍼 생성 시간 개선

서버를 시작할때 BUFFER AREA 에서 메모리 할당시 성능이 느린 문제를 개선하였습니다.

###### Delete 성능 개선

내부적으로 Delete 로깅하는 부분이 변경되어, DB 바이너리 버전이 6.5.1 에서 6.7.1 로 변경되었다. 

###### Partition insert시 Execution memory 최적화

단순 insert의 경우, Execution memory 사용량을 줄이도록 개선하였다.

###### Disk partition table의 prepared memory 사용량 개선

Partition table의 DML 수행시 사용되는 prepare memory 사용량을 줄이도록 개선하였다.

###### 힌트 추가

정규화 형태, 조인방법, 조인순서, 테이블 접근방법, 병렬 질의 처리에 대한 힌트가
추가되었다.  

* PLAN_CACHE_KEEP
* SERIAL_FILTER



##### 2.1.4.2 자원 효율성

###### InfiniBand 지원

통신 성능 향상을 위해 RDMA(Remote Direct Memory Access) 통신 기반인 Infiniband를 지원한다.

#### 2.1.5 고가용성

##### DDL PVO 안정성 개선 

DDL PVO 단계에서의 안정성을 개선하였습니다.

#### 2.1.6 기타

##### 2.1.6.1 그 외 변경사항

###### Altibase Sharding 2.0 지원 중단

7.1에서 제공했던 Sharding 기능은 더이상 지원하지 않는다.

###### JAVA 1.8 지원

JDK, JRE 1.8 이상을 지원하며, JDK 1.7 이하는 더이상 지원하지 않는다.

ALA protocol 변경

### 2.2 변경 사항

DBA와 개발자가 알아야 할 추가, 변경, 및 제거된 기능을 아래에서 설명한다.

#### Altibase JDBC 4.2 변경 사항

Altibase JDBC 4.2는 Altibase JDBC 3.0 에 대해 하위 호환성을 보장하지만 일부 인터페이스의 경우 JDBC API Specification 4.2에 따라 동작이 변경되었다.

###### 미지원 기능에 대한 예외 처리 클래스 변경

다음 인터페이스에 대한 예외 처리 클래스가 SQLException에서 SQLFeatureNotSupportedException으로 변경되었다. SQLFeatureNotSupportedException은 SQLException의 하위 클래스이므로 기존 사용자 프로그램은 수정없이 그대로 동작한다.

- Altibase.jdbc.driver.AltibaseConnection
  - setTypeMap(Map)

- Altibase.jdbc.driver.AltibaseStatement
  - setCursorName(String)

- Altibase.jdbc.driver.AltibasePreparedStatement
  - setArray(int, Array) 
  - setRef(int, Ref)
  - setURL(int, URL)
  - setUnicodeStream(int, InputStream, int)

- Altibase.jdbc.driver.Blob
  - position(Blob, long)
  - position(byte[], long)
- Altibase.jdbc.driver.Clob
  - position(Clob, long)
  - position(String, long)

- Altibase.jdbc.driver.CallableStatement
  - getArray(int)
  - getObject(int, Map)
  - getRef(int)
  - getURL(int)

- Altibase.jdbc.driver.AltibaseDatabaseMetaData
  - getColumnPrivileges(String, String, String, String)
  - getUDTs(String, String, String, int[])

- Altibase.jdbc.driver.AltibaseResultSet
  - getCursorName()
  - getArray(int)
  - getObject(int, Map)
  - getRef(int)
  - getURL(int)
  - getUnicodeStream(int)
  - updateArray(int, Array)
  - updateRef(int, Ref)

###### DatabaseMetaData의 일부 인터페이스 결과에 항목 추가

getProcedures(), getProcedureColumns(), getFunctions(), getFunctionColumns() 인터페이스 결과에 SPECIFIC_NAME 컬럼이 추가되었다. 

Altibase JDBC 7.2 에서 SPECIFIC_NAME은 다음과 같은 형태로 구현하였다.

```java
ProcName(FuncName) + '_' + ouid
```

###### 연결 속성 기본값 변경

- reuse_resultset 
- lob_null_select 

###### JDBC 4.2만을 위한 JDBC 속성 추가

- getprocedures_return_functions

###### CLIENT_TYPE 변경

- v$session 뷰의 CLIENT_TYPE이 NEW_JDBC 에서 NEW_JDBC42로 변경되었다.

#### 데이터베이스 버전

데이터베이스 구성 요소 별 버전

| Altibase 버전 | 데이터베이스 바이너리 버전 | 통신 프로토콜 버전 | 메타 버전 | 이중화 프로토콜 버전 | 샤딩 버전 |
| ------------- | -------------------------- | ------------------ | --------- | -------------------- | --------- |
| 7.1.0.1.2     | 6.5.1                      | 7.1.6              | 8.5.1     | 7.4.2                | 2.0.0     |
| 7.2.0.0.0     | 6.7.1                      |                    |           |                      |           |

#### 호환성

##### 데이터베이스 바이너리 버전

데이터베이스 바이너리 버전은 데이터베이스 이미지 파일과 로그 파일의 호환성을 나타낸다. 데이터베이스 이미지 및 로그 파일의 형식이 변경되었으므로, 데이터베이스 업그레이드 시 기존 데이터베이스는 마이그레이션 되어야 한다.

| Altibase 버전 | 데이터베이스 바이너리 버전 |
| ------------- | -------------------------- |
| 7.1.0.1.2     | 6.5.1                      |
| 7.2.0.0.0     |                            |

##### 통신 프로토콜 버전

통신 프로토콜 버전이 변경되었다. Patch 버전(세번째 자리 버전)이 변경되어, Altibase 7.1에서 동작하도록 빌드된 클라이언트 응용 프로그램은 Altibase 7.2와 호환이 된다. 즉, 다시 빌드하지 않아도 된다.

| Altibase 버전 | 통신 프로토콜 버전 |
| ------------- | ------------------ |
| 7.1.0.1.2     | 7.1.6              |
| 7.2.0.0.0     |                    |

##### 메타 버전

메타 버전이 변경되었다. Altibase 7.1 이하 버전에서 Altibase 7.2로 업그레이드 시, 자동으로 메타 업그레이드가 수행된다.?????(확인필요) 하지만, 업그레이드를 롤백하려는 경우에는 메타를 재구성해야 한다.

| Altibase 버전 | 메타 버전 |
| ------------- | --------- |
| 7.1.0.1.2     | 8.5.1     |
|               |           |

##### 이중화 프로토콜 버전

이중화 프로토콜 버전이 변경되지 않았다. 따라서 Altibase 6.5.1 과 7.1.0.1.2 간의 이중화가 가능하다.

| Altibase 버전 | 이중화 프로토콜 버전 |
| ------------- | -------------------- |
| 7.1.0.1.2     | 7.4.2                |
| 7.2.0.0.0     |                      |

##### 샤딩 버전

| Altibase 버전 | 샤딩 버전 |
| ------------- | --------- |
| 7.2.0.0.0     |           |

#### 프로퍼티

Altibase 7.2.0.0.0 에서는 아래의 프로퍼티들이 추가, 변경, 삭제되었다.  
각 프로퍼티에 대한 자세한 내용은 [*General Reference*](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_2.md) 를 참고하기 바란다.

##### 새로운 프로퍼티

-   REPLICATION_GAP_UNIT
-   JOB_MSGLOG_FILE
-   JOB_MSGLOG_SIZE
-   JOB_MSGLOG_COUNT
-   JOB_MSGLOG_FLAG
-   IB_ENABLE
-   IB_PORT_NO
-   IB_MAX_LISTEN
-   IB_LISTENER_DISABLE
-   IB_LATENCY
-   IB_CONCHKSPIN
-   REPLICATION_DDL_SYNC
-   REPLICATION_DDL_SYNC_TIMEOUT
-   REPLICATION_IB_PORT_NO
-   REPLICATION_IB_LATENCY
-   MATHEMATICS_TEMP_MEMORY_MAXIMUM
-   SERIAL_EXECUTE_MODE
-   REPLICATION_META_ITEM_COUNT_DIFF_ENABLE
-   DISK_HASH_COST_METHOD
-   INIT_TOTAL_WA_SIZE

##### 변경된 프로퍼티

- EXECUTE_STMT_MEMORY_MAXIMUM

  기본값이 1073741824에서 2147483648로 변경되었다.

- EXECUTOR_FAST_SIMPLE_QUERY

  기본값이 0에서 2로 변경되었다.

- INDEX_MAXTRANS

  기본값이 30에서 50으로 변경되었다.

- MEMORY_INDEX_BUILD_RUN_SIZE

  기본값이 32768에서 131072로 변경되었다.

- PSM_CHAR_DEFAULT_PRECISION

  기본값이 32767에서 32000으로 변경되었다.

- PSM_NCHAR_UTF16_DEFAULT_PRECISION

  기본값이 16383에서 16000으로 변경되었다.

- PSM_NCHAR_UTF8_DEFAULT_PRECISION

  기본값이 10921에서 10666으로 변경되었다.

- PSM_NVARCHAR_UTF16_DEFAULT_PRECISION

  기본값이 16383에서 16000으로 변경되었다.

- PSM_NVARCHAR_UTF8_DEFAULT_PRECISION

  기본값이 10921에서 10666으로 변경되었다.

- PSM_VARCHAR_DEFAULT_PRECISION

  기본값이 32767에서 32000으로 변경되었다.

- ARITHMETIC_OPERATION_MODE

  MAX 값이 2에서 3으로 변경되었다.

- EXECUTOR_FAST_SIMPLE_QUERY

  MAX값이 1에서 2로 변경되었다.

- INDEX_INITRANS

  MAX값이 30에서 50으로 변경되었다.

- INDEX_MAXTRANS

  MAX값이 30에서 50으로 변경되었다.

- LOB_CACHE_THRESHOLD

  MAX값이 8192에서 524288 로 변경되었다.

- HASH_AREA_SIZE

  MIN값이 524288에서 3145728로 변경되었다.

- TOTAL_WA_SIZE

  MIN값이 524288에서 0으로 변경되었다.

##### 삭제된 프로퍼티

-   LOCK_MGR_TYPE
-   LOCK_MGR_SPIN_COUNT
-   LOCK_MGR_MIN_SLEEP
-   LOCK_MGR_MAX_SLEEP
-   LOCK_MGR_DETECTDEADLOCK_INTERVAL
-   TEMP_MAX_PAGE_COUNT
-   SHARD_META_ENABLE

#### 메타 테이블

##### 새로운 메타테이블

* SYS_REPL_RECEIVER_
* SYS_REPL_ITEMS_HISTORY_
* SYS_GEOMETRIES_
* SYS_GEOMETRY_COLUMNS_
* USER_SRS_

##### 변경된 메타테이블

* SYS_REPLICATIONS_
* SYS_REPL_HOSTS_
* SYS_REPL_ITEMS_
* SYS_REPL_OLD_ITEMS_
* SYS_REPL_OLD_COLUMNS_

##### 삭제된 메타테이블

아래의 메타 테이블이 삭제되었다.

-   STO_COLUMNS_
-   STO_USER_COLUMNS_
-   STO_SRS_
-   STO_PROJCS_
-   STO_PROJECTIONS_
-   STO_GEOGCS_
-   STO_GEOCCS_
-   STO_DATUMS_
-   STO_ELLIPSOIDS_
-   STO_PRIMEMS_

#### 성능 뷰

아래의 성능 뷰 들이 추가되었다.  

각 성능 뷰에 대한 자세한 내용은 [*General Reference*](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md)를 참고하기 바란다.

##### 새로운 성능 뷰

-   [V$LIBRARY](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#vlibrary)
-   [V$PROCINFO](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#vprocinfo)

##### 수정된 성능 뷰

- [V$DISK_TEMP_STAT](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_3.md#vdisk_temp_stat)   - BUG-48369 관련. 패치노트 7.1.0.5.1 문의

  | Column name        | 변경내역 |
  | ------------------ | -------- |
  | OVER_ALLOC_COUNT   |          |
  | MAX_WORK_AREA_SIZE |          |
  | RUNTIME_MAP_SIZE   |          |

- [V$REPGAP](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#vrepgap)

  | Column name  | 변경내역                                                     |
  | ------------ | ------------------------------------------------------------ |
  | REP_GAP      | 컬럼 변경</br> 이중화 갭에 해당하는 로그파일의 실제 사이즈 (단위: 프로퍼티 [REPLICATION_GAP_UNIT](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_2.md#replication_gap_unit-단위-바이트)에 설정된 단위) |
  | REP_GAP_SIZE | 컬럼 추가(BIGINT)</br> 이중화 갭의 로그파일 사이즈를 의미하며, BYTE 단위이다. |

- [V$REPGAP_PARALLEL](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#vrepgap_parallel)

  | Column name  | 변경내역                                                     |
  | ------------ | ------------------------------------------------------------ |
  | REP_GAP      | 컬럼 변경</br> 이중화 갭에 해당하는 로그파일의 실제 사이즈 (단위: 프로퍼티 [REPLICATION_GAP_UNIT](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_2.md#replication_gap_unit-단위-바이트)에 설정된 단위) |
  | REP_GAP_SIZE | 컬럼 추가(BIGINT)</br> 이중화 갭의 로그파일 사이즈를 의미하며, BYTE 단위이다. |

- [V$STATNAME](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#vstatname) 

  IB(Infiniband) 관련 통계 정보가 추가되었다

  read IB count, write IB count, byte received via IB, byte sent via IB

- V$STATEMENT

  | Column name             | 변경내역                                                     |
  | ----------------------- | ------------------------------------------------------------ |
  | MATHEMATICS_TEMP_MEMORY | 컬럼 추가(BIGINT)</br> 분석함수에서 사용하는 MATHEMATICS TEMP 메모리 사용량를 보여준다. |

-   V$SESSION

| Column name             | 변경내역                                                   |
| ----------------------- | ---------------------------------------------------------- |
| MESSAGE_CALLBACK        | 컬럼 추가(VARCHAR(7))</br> 클라이언트 메시지 콜백 등록상태 |
| REPLICATION_DDL_SYNC    | 컬럼 추가(INTEGER)</br> 이중화 중 DDL 복제 여부            |
| REPLICATION_DDL_TIMEOUT | 컬럼 추가(BIGINT)</br> DDL복제 타임아웃                    |

* V$TRANSACTION

| Column name                                                  | 변경내역                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [PROCESSED_UNDO_TIME](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#processed_undo_time) | 컬럼 추가(INTEGER)</br>언두 시작 시점부터 현재까지 진행된 시간 (초) |
| [ESTIMATED_TOTAL_UNDO_TIME](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#estimated_total_undo_time) | 컬럼 추가(INTEGER)</br>언두 완료될때 까지 추정되는 총 소요 시간 (초) |
| [TOTAL_LOG_COUNT](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#total_log_count) | 컬럼 추가(BIGINT)</br>한 트랜잭션의 모든 로그 갯수           |
| [TOTAL_UNDO_LOG_COUNT](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#total_undo_log_count) | 컬럼 추가(BIGINT)</br>한 트랜잭션에서 앞으로 진행되야할 총 언두 로그의 갯수 |
| [PROCESSED_UNDO_LOG_COUNT](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/GeneralReference_4.md#processed_undo_log_count) | 컬럼 추가(BIGINT)</br>한 트랜잭션에서 언두완료된 로그 갯수   |

### 2.3 패키지

| OS    | CPU                       | Archive Name                                                                                                             |
|-------|---------------------------|--------------------------------------------------------------------------------------------------------------------------|
| AIX   | PowerPC                   | altibase- server-7.1.0.1.2-AIX-POWERPC-64bit-release.run                                                                 |
|       |                           | altibase- client-7.1.0.1.2-AIX-POWERPC-64bit-release.run                                                                 |
| HP-UX | IA64                      | altibase- server-7.1.0.1.2-HPUX-IA64-64bit-release.run                                                                   |
|       |                           | altibase- client -7.1.0.1.2-HPUX-IA64-64bit-release.run                                                                  |
| LINUX | X86                       | altibase- server-7.1.0.1.2-LINUX-X86-64bit-release.run                                                                   |
|       |                           | altibase- client-7.1.0.1.2-LINUX-X86-64bit-release.run                                                                   |
|       | PowerPC                   | altibase- server-7.1.0.1.2-LINUX-POWERPC-64bit-release.run                                                               |
|       |                           | altibase- client-7.1.0.1.2-LINUX-POWERPC-64bit-release.run                                                               |
|       | PowerPCLE (Little Endian) | altibase- server-7.1.0.1.2-LINUX-POWERPCLE-64bit-release.run                                                             |
|       |                           | altibase- client-7.1.0.1.2-LINUX-POWERPCLE-64bit-release.run                                                             |

### 2.4 다운로드

#### Package

http://support.altibase.com

#### Manual

https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/README.md

#### 설치

[Altibase Installation Guide](https://github.com/ALTIBASE/Documents/blob/master/Manuals/Altibase_trunk/kor/Installation.md) 참고