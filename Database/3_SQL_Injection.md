## SQL Injection



- 해커에 의해 조작된 SQL 쿼리문이 DB에 그대로 전달되어

  비정상적 명령을 실행시키는 공격 기법



##### 공격 방법

1. 인증 우회

   ㄱ. 로그인 시 INPUT 칸에 ID, PASSWORD 입력하고 인증을 요구할 것

   ​	 그 때 아래와 같은 쿼리문이 전송될 것

   ```sql
   SELECT * FROM USER WHERE ID = "kyw" AND PASSWORD = "1234";
   ```

    	이 때, PASSWORD INPUT 칸에 아래와 같이 입력한다면

   ```sql
   1234; DELETE * USER FROM ID = "1";
   ```

   ​	보안 처리가 되지 않은 경우, 아래와 같은 쿼리문이 전송되어

   ​	DB에 원치 않는 접근 및 수정을 초래할 수 있다.

   ```sql
   SELECT * FROM USER WHERE ID = "kyw" AND PASSWORD = "1234";
   DELETE * USER FROM ID = "1";
   ```

   ㄴ. 기본 쿼리문의 WHERE 절에 OR 문을 추가하여 `'1' = '1'` 같은 true문을 작성하여,

   ​	무조건 적용되도록 수정한 뒤 DB를 마음대로 조작할 수도 있다





2. 데이터 노출

   - 시스템에서 발생하는 에러 메시지를 통해서 시스템 정보를 빼낸 후,

     그를 활용하여 공격하는 방법

     => 해커는 악의적인 구문을 삽입하여 에러를 유발하고, 시스템 정보를 파악





##### 방어 방법

1. input 값 받을 때, 특수문자 여부 검사

   - 로그인 전, 검증 로직을 통하여 미리 설정한 문자가 들어올 때 이를 거부

2. SQL 서버 오류 발생 시, 해당하는 에러 메시지를 숨기기

   - view를 활용하여 일반 사용자는 view에만 접근할 수 있게 조치

     => <u>원본 DB 테이블에는 접근 권한이 있는 사람만 접근이 가능하게끔</u>

3. preparedstatement

   - 특정 쿼리문의 템플릿을 정해놓고, 이에 사용될 변수를 외부 입력으로 받는 것을 의미

     => 쿼리문을 input으로 전달하더라도 이는 매개변수에 담기기 때문에

     ​     쿼리문으로서 효력이 발생하지 않는다.