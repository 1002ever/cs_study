## 이상(Anomaly)



- 종류

  ㄱ. 삽입 이상 ( Insertion Anomaly )

  ㄴ. 갱신 이상 ( Update Anomaly )

  ㄷ. 삭제 이상 ( Deletion Anomaly )



1. 삽입 이상

   - 스키마 설계 상의 문제로

     불필요한 데이터를 추가해야지만 삽입할 수 있는 상황



2. 갱신 이상

   - 어떤 레코드 일부 값 수정 시,

     그 값을 참조하는 다른 테이블에서도 모두 갱신이 이뤄져야 한다.

     => 이 때, '일부'만 갱신되어 <u>데이터가 불일치하는 모순이 발생하는 상황</u>



3. 삭제 이상
   - 튜플 삭제로 인해 삭제를 원치 않는 데이터까지 함께 지워지는 상황





#### *이상 해결 방법*

- 정규화

  => 데이터 중복을 줄이는 것

  ​     단, 데이터 중복을 너무 줄이면 효율적인 데이터 활용이 불가

  ​     <u>때문에 의도적으로 적당한 비정규화를 수행하기도 함</u>