# 트랜잭션과 잠금

+ 잠금과 트랜잭션, 트랜잭션의 격리수준
+ MySQL에서 트랜잭션이란?
+ 트랜잭션 사용 시 주의사항
+ MySQL 엔진의 잠금 (Lock) 4가지가 각각의 특징과 어떤 경우에 사용되는지
  + 글로벌 락
  + 테이블 락
  + 네임드 락
  + 메타데이터 락
  
![image](https://user-images.githubusercontent.com/76584547/168422836-bbc55e31-c461-44f3-90ef-4717e65a828e.png)


+ InnoDB 스토리지 엔진 잠금 (Lock) 각각의 특징
  + 레코드 락
  + 갭 락
  + 넥스트 키 락
  + 자동 증가 락
+ 인덱스와 잠금의 특징
+ 레코드 수준의 잠금 확인 및 해제 특징, 잠금과 잠금 대기 순서 확인 방법
+ MySQL의 격리 수준 각각의 특징과 조회 결과 
  + READ UNCOMMITTED
  + READ COMMITTED
  + REPEATABLE READ
  + SERIALIZABLE
