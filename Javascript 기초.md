# Javascript  기초

- 변수 선언

  - let: 변할 수 있는 값
  - const: 변하지 않는 값

  1. 변수는 문자, 숫자, $, _만 사용 가능
  2. 첫 글자는 숫자가 될 수 없음
  3. 예약어는 사용할 수 없음
  4. 상수는 대문자로 알려 주기   예) const MAX_SIZE = 99;
  5. 변수명은 읽기 쉽고 이해할 수 있게 선언

  - 앞에 \을 넣어 주면 특수 문자 인식
  - ${변수}, ${표현식}

- 숫자는 사칙연산 가능

- typeof 연산자: 변수의 자료형을 알아냄 예) console.log(type of "안녕")

  

- 형 변환 (**대문자**로 쓰기)

  - String() -> 문자형으로 변환
  - Number() -> 숫자형으로 변환
    - true, false는 1, 0으로 변환
    - 문자는 NaN으로 변환
    - Number(null) -> 0, Number(undefined) -> NaN
  - Boolean() -> 불리언형으로 변환
    - false: 숫자 0, 빈 문자열 "", null, undefined, NaN
    - true: 문자 0, 공백

  ------

- alert: 알림

- prompt: 입력받음 -> 입력받은 값은 문자형

  ![image-20220719233337612](C:\Users\kiwio\AppData\Roaming\Typora\typora-user-images\image-20220719233337612.png)

  - 두 개의 값을 인수로 받을 수 있음 => 뒤의 값은 디폴트 값이 된다

    ![image-20220719233507649](C:\Users\kiwio\AppData\Roaming\Typora\typora-user-images\image-20220719233507649.png)

- confirm: 확인받음

  - 확인과 취소 버튼 있음 => 확인이면 true, 취소면 false

  ![image-20220719233553504](C:\Users\kiwio\AppData\Roaming\Typora\typora-user-images\image-20220719233553504.png)

- 단점: 스크립트 일시 정지, 스타링 X