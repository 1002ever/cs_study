## Key



- 검색, 정렬 시 Tuple 을 구분할 수 있는 기준이 되는 속성



1. 후보키(Candidate Key)

   - 튜플을 유일하게 식별하기 위해 사용하는 속성들의 부분 집합

     => 기본키의 후보군인 셈

   - 2가지 조건이 필수적

     ㄱ. 유일성 : Key 로 하나의 튜플을 유일하게 식별 가능

     ㄴ. 최소성 : 꼭 필요한 속성으로만 구성

     

2. 기본키(Primary Key)

   - 후보키 중 선택한 메인 키

   - 특징

     ㄱ. Null 값을 가질 수 없음

     ㄴ. 중복값을 가질 수 없음

     

3. 대체키(Alternate Key)

   - 후보키 중 기본키를 제외한 키 = **보조키**

     

4. 슈퍼키(Super Key)

   - 유일성은 만족, 최소성은 만족하지 못하는 키