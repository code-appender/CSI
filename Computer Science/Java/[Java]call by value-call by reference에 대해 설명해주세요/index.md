
## [Java]call by value, call by reference에 대해 설명해주세요
`함수 호출 방법의 차이`
- Call by Value(값에 의한 호출)
  - JAVA는 기본적으로 참조값을 담은 레퍼런스 변수를 복사하는 Call-by-Value로 수행된다.
  - 함수 호출시에 데이터 자체가 복사 되어 이동해서 메모리 공간을 더 잡아 먹는다

- Call by Reference(참조에 의한 호출)
  - C/C++와 같이 변수의 주소값 자체를 가져올 방법이 없으며, 이를 넘길 수 있는 방법 또한 있지 않다.
  - 원본 값의 메모리 주소를 복사하여 전달합니다.
  - Call By Reference로 전달된 값은 함수 실행 유무와 상관 없이 존재합니다.
  - 함수 내에서 생긴 변경 사항이, 함수 외부의 외부의 값에 영향을 줍니다.
  
- Q. 근데 자바에도 주소값을 전달하는 경우가 있지 않느냐? 
  - c언어에서는 주소값 자체를 변경할 수 있지만 자바는 주소값 자체에 대한 변경이 아니라 객체에 대한 참조(주소)를 전달하여 상태를 변화시키는것이므로 다르다 
  - (주소값을 직접 조작하거나 변경할 수 없다!의 관점, 그래서 자바에서는 call by address 와 같은 개념으로 불리는 경우도 있다고 한다.)
  - 원본객체의 프로퍼티에는 접근이 가능하지만 원본 객체 자체를 변경하는것은 불가능하다 

[참고1](https://gyoogle.dev/blog/computer-language/Java/Call%20by%20value%20&%20Call%20by%20reference.html)  
[참고2](https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%9E%90%EB%B0%94%EB%8A%94-Call-by-reference-%EA%B0%9C%EB%85%90%EC%9D%B4-%EC%97%86%EB%8B%A4-%E2%9D%93)  