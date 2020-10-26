## SQL JOIN



- 두 개 이상의 테이블이나 DB를 연결하여 데이터를 검색하는 방법

  => <u>연결하려면 적어도 하나 이상의 컬럼을 서로 공유하고 있어야 함</u>



- JOIN 종류
  - INNER JOIN
  - LEFT OUTER JOIN
  - RIGHT OUTER JOIN
  - FULL OUTER JOIN
  - CROSS JOIN
  - SELF JOIN



1. INNER JOIN

   - 교집합	

     ```sql
     SELECT
     A.NAME, B.AGE
     FROM EX_TABLE A
     INNER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
     ```

     

2. LEFT OUTER JOIN

   - 왼쪽 기준으로 JOIN

     ```sql
     SELECT
     A.NAME, B.AGE
     FROM EX_TABLE A
     LEFT OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
     ```



3. RIGHT OUTER JOIN

   - 오른쪽 기준으로 JOIN

     ```sql
     SELECT
     A.NAME, B.AGE
     FROM EX_TABLE A
     RIGHT OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
     ```



4. FULL OUTER JOIN

   - 합집합

     ```sql
     SELECT
     A.NAME, B.AGE
     FROM EX_TABLE A
     FULL OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
     ```



5. CROSS JOIN

   - 각 테이블 튜플 조합의 모든 경우의 수를 표현

     A 튜플이 3, B 튜플이 4개면 => 12개의 튜플이 생성

     ```sql
     SELECT
     A.NAME, B.AGE
     FROM EX_TABLE A
     CROSS JOIN JOIN_TABLE B
     ```

     

6. SELF JOIN

   - 자기자신과 조인

   - 자시자신과 CROSS JOIN 하는 느낌

     ```sql
     SELECT
     A.NAME, B.AGE
     FROM EX_TABLE A, EX_TABLE B
     ```

     