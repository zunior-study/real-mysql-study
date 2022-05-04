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
|Week 02|MySQL 아키텍처| <a href="">[라영지]</a> <br> <a href="https://github.com/minyul">[민율]</a> <br> <a href="">[최정헌]</a> <br>  <a href="https://github.com/zunior-study/real-mysql-study/tree/main/%ED%98%84%EA%B1%B4%EC%88%98/01.%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98">[현건수] - GitHub </a> <br> |

### 질문 목록
#### 1주차 - Mysql 아키텍처
- 포그라운드 쓰레드와 백그라운드 쓰레드 차이는 무엇인가?
- MySQL엔진과 스토리지엔진의 역할을 말해보시오
- MySQL 성능 상의 이유로 읽기 작업과 쓰기 작업의 처리 방식이 다른데, 이 부분에 대해서 알고 있는가?
- DB는 ACID를 유지해야하는데 DML(INSERT, DELETE, UPDATE) 작업 시 버퍼풀로 올릴 경우, 서버가 장애날 경우 어떤 식으로 데이터를 보장하는가?
- DML(INSERT, DELETE, UPDATE) 작업 시 리두로그와 언두로그의 데이터 변경을 설명해보시오
- 데드락 감지 쓰레드에 대해 설명해보고, 데드락 시 어떤 기준으로 트랜잭션을 종료하는지 설명해보시오
- MVCC의 개념을 설명해주세요
- 쿼리 실행 구조를 설명해주세요
- 언두로그 사용시 여러 트랜잭션이 길어질 때, 메모리 사용량 주의사항을 설명해보시오
