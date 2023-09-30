
## [JAVA] == 연산과 Object.Equals() 연산의 차이에 대해서 설명해주세요

`==`연산 
- 원시 타입(Primitive Type)의 경우 값에 대한 비교를 진행하고 참조 타입(Reference Type)의 경우 주소값을 비교하는 연산입니다.
- 즉, 메모리 내의 동일한 위치 인지를 비교합니다.

`equals() `연산
- 객체의 내용(값)을 비교할때 사용됩니다. 
- 일반적으로 클래스에서 오버라이딩 되어 해당 클래스의 객체가 다른 객체와 동등한지 판별할 수 있도록 수현됩니다. 
- equals()메서드는 객체의 동등성을 정의합니다.
- Q. 언제 equals를 정의해야할까. equals를 정의하는 방법 [link](https://velog.io/@sonypark/Java-equals-hascode-%EB%A9%94%EC%84%9C%EB%93%9C%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%9E%AC%EC%A0%95%EC%9D%98%ED%95%B4%EC%95%BC-%ED%95%A0%EA%B9%8C)