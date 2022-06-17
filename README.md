# 📚 Real Mysql 8.0 스터디

### 모티브
+ **자유**, **함께** 그리고 **완주**

### 멤버
+ [라영지](https://github.com/Rayoungji)
+ [민율](https://github.com/minyul)
+ [최정헌](https://github.com/iiaii)
+ [현건수](https://github.com/hgs-study)

### 진행안
+ 토론형 스터디
+ 각 챕터 내용 자유롭게 정리 (플랫폼 상관없이)
+ 토론시, 공부하면서 느꼈던 중요사항 질문 2~3가지 준비

### 정리
|No. <img width=150/>|주제 <img width=200/>| 정리 자료 <img width=400/>|
|---|---|---|
|Week 01|사전 모임| - |
|Week 02|MySQL 아키텍처| <a href="">[라영지]</a> <br> <a href="https://github.com/minyul">[민율]</a> <br> <a href="">[최정헌]</a> <br>  <a href="https://github.com/zunior-study/real-mysql-study/tree/main/%ED%98%84%EA%B1%B4%EC%88%98/01.%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98">[현건수] - GitHub</a> <br> |
|Week 03|트랜잭션과 잠금| <a href="">[라영지]</a> <br> <a href="https://github.com/minyul">[민율]</a> <br> <a href="">[최정헌]</a> <br>  <a href="https://github.com/zunior-study/real-mysql-study/tree/main/%ED%98%84%EA%B1%B4%EC%88%98/02.%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98%EA%B3%BC%20%EC%9E%A0%EA%B8%88">[현건수] - GitHub</a> <br> |
|Week 04|인덱스| <a href="">[라영지]</a> <br> <a href="https://github.com/minyul">[민율]</a> <br> <a href="">[최정헌]</a> <br>  <a href="https://github.com/zunior-study/real-mysql-study/tree/main/%ED%98%84%EA%B1%B4%EC%88%98/03.%20%EC%9D%B8%EB%8D%B1%EC%8A%A4">[현건수] - GitHub</a> <br> |
|Week 05|옵티마이저와 힌트| <a href="">[라영지]</a> <br> <a href="https://github.com/minyul">[민율]</a> <br> <a href="">[최정헌]</a> <br>  <a href="https://github.com/zunior-study/real-mysql-study/tree/main/%ED%98%84%EA%B1%B4%EC%88%98/04.%EC%98%B5%ED%8B%B0%EB%A7%88%EC%9D%B4%EC%A0%80%EC%99%80%20%ED%9E%8C%ED%8A%B8_1">[현건수] - GitHub</a> <br> |


### 질문 목록
### 1주차 - Mysql 아키텍처
- 포그라운드 쓰레드와 백그라운드 쓰레드 차이는 무엇인가?
- MySQL엔진과 스토리지엔진의 역할을 말해보시오
- MySQL 성능 상의 이유로 읽기 작업과 쓰기 작업의 처리 방식이 다른데, 이 부분에 대해서 알고 있는가?
- DB는 ACID를 유지해야하는데 DML(INSERT, DELETE, UPDATE) 작업 시 버퍼풀로 올릴 경우, 서버가 장애날 경우 어떤 식으로 데이터를 보장하는가?
- DML(INSERT, DELETE, UPDATE) 작업 시 리두로그와 언두로그의 데이터 변경을 설명해보시오
- 데드락 감지 쓰레드에 대해 설명해보고, 데드락 시 어떤 기준으로 트랜잭션을 종료하는지 설명해보시오
- MVCC의 개념을 설명해주세요
- 쿼리 실행 구조를 설명해주세요
- 언두로그 사용시 여러 트랜잭션이 길어질 때, 메모리 사용량 주의사항을 설명해보시오

<BR>
    
### 2주차 - 트랜잭션과 잠금

- 격리 레벨 4단계를 설명해보시오
    - 더티리드
    - 넌 리피터블 리드
    - 팬텀 리드
- 갭락과 넥스트 키락 개념
- InnoDB의 레코드 락 방식을 설명해주시오
    - 인덱스가 하나도 없을 경우 동작 방식
- 테이블락이 InnoDB에 영향을 주지 않는데, 특정 상황엔 테이블락이 걸린다. 이 특정 상황은?
- 만약에 DB 서버 1대고 , APP 서버 5대 → DB 동기화시켜야한다 . 이 동기화 방법은?
- READ-COMMITED에서 더티리드 현상을 어떻게 막았는지?
- REPEATABLE-READ는 기본적으로 SELECT는 트랜잭션 범위 내에서 작동한다 그 이유는? (READ-COMMITED는 트랜잭션 내에서 실행되는 SELECT 문장과 트랜잭션 외부에서 실행되는 SELECT 문장의 차이가 별로 없다.)
    - (답안)
    - 트랜잭션 번호 → 트랜잭션 내에 EX) 10번 → 깨지는것
    - 트랜잭션 번호도 언두로그 저장하기 때문에 트랜잭션 외부에서 동작하면
    - 언두로그에 있는 자신의 트랜잭션 번호보다 낮은 트랜잭션 번호 데이터를 읽어드리기 때문에

<BR>

### 3주차 - 인덱스

- 테이블 풀스캔과 인덱스 레인지 스캔의 I/O방식 특징
    - 순차 I/O, 랜덤 I/O
- 많은 자료구조가 있는데 인덱스가 왜 B-TREE를 사용하나?
- 클러스터링 인덱스 VS 넌 클러스터링 인덱스
- 커버링 인덱스 설명
    - INDEX (A) → SELECT A
- InnoDB 스토리지 엔진이 클러스터링 키를 가지는 조건
    - 프라이머리 키 → 클러스터링 키
    - 유니크 키 → 제일 첫번째 키가 클러스터링 키
    - x → 레코드마다 내부적으로 일련번호 클러스터링 키
- 복합인덱스, 선행 컬럼이 where 없으면 어떤 인덱스, 설명?
    - INDEX(A,B)
    - SELECT * FROM TABLE WHERE B= 10;
    - [조건]인덱스 스킵 스캔 → MySQL 8.0, 커버링 인덱스
- 복합인덱스, 5.7인경우 선행 컬럼이 없을 경우 어떻게 되는지?
    - 선행 컬럼이 없으면 안타고
    - INDEX(A,B) 있을 경우 LIKE(”%”)를 사용할 경우
- 클러스터링 인덱스 구조가 B-TREE인데, 다른점
    - 클러스터링 - 데이터 레코드를 가지고 있다
- 클러스터링 인덱스 vs 세컨더리 인덱스 데이터를 찾아가는 방식
- InnoDB와 MyISAM의 세컨더리 인덱스로 검색할 때의 차이점
    - MyISAM은 인덱스를 검색해 레코드의 주소를 확인하고, 레코드의 주소로 최종 레코드를 가져옴
    - InnoDB : 인덱스를 검색해 레코드의 프라이머리 키 값을 확인하고, 프라이머리 키 인덱스를 검색해서 최종 레코드를 가져옴
- 유니크 인덱스 vs 세컨 인덱스
    - 유니크, 세컨더리 인덱스 중에 유니크 더 빠르다(?)
    - 검색
    - 쓰기
        - 세컨더리 : 더 빠르다고 ⇒ 체인지 버퍼를 통해 버퍼링
        - 유니크 : 무조건 중복체크 ⇒ 더  느리다
        - 읽기랑 쓰기 잠금이 데드락 빈번
- 작업 범위 결정 조건 / 체크 조건으로 사용할 수 없는 인덱스 조건
- 클러스터링 인덱스의 장단점
- 외래키 DELETE CASCADE 설명 ?

<BR>

### 4주차 - 옵티마이저와 힌트
- 쿼리 실행 순서에 대해 설명해주세요
- InnoDB 엔진으로 테이블 풀스캔 할 때, 빠른 처리를 위해 리드 어헤드를 사용하는데, 리드 어헤드를 설명해주세요
- 정렬 시, 소트버퍼와 디스크에 저장하면서 사용하는데, 이를 `멀티 머지` 라고 하는데 간단하게 설명해주세요.
- 정렬을 처리하는 방법중 filesort 사용시 소트 버퍼를 사용하게되는데 이때 싱글 패스, 투 패스 각각의 장단점에 대해 설명해주세요.
- `select * from bigtable` 같은 쿼리를 싱행하면, MySQL 서버는 스트리밍 방식을 사용하지만 JDBC 라이브러리가 버퍼링 방식을 사용하는 이유는?
    
