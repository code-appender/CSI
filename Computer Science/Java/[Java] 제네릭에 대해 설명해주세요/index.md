- 제네릭(Generic)이란 데이터의 타입을 **일반화한다**는 것을 의미
  ```java
  List<Integer> list1 = new ArrayList<>();
  List list2 = new ArrayList<>();
  Map<String, String> map = new ArrayList<>();
  ```
- 위와같이 꺽쇠안에 클래스 타입이 명시된 패턴이 **제네릭 파라미터**
  - 타입 파라미터로 명시할 수 있는 것은 참조타입 뿐.<br>
    ex) `Integer`, `String`, 클래스, 인터페이스 등
  - 원시 타입(int, double, char, long)은 올 수 없음
- 파라미터 타입이나 리턴 타입에 대한 정의를 외부로 미뤄 컴파일 시 미리 지정하는 방법

### 제네릭의 특징
- 클래스 혹은 메소드에 선언 가능
  -  클래스에 제네릭을 선언하는 방법<br>: 클래스 우측에 제네릭 파라미터를 선언
  ```java
  class test<T>{
    public T example; 
  }
  ```
  - 메소드에 선언하는 방법<br>: 제네릭 타입이 메소드 호출시점에 결정되야 할 경우 사용, 파라미터 타입에 따라 제네릭 타입이 결정되기 때문에 다이나믹한 처리가 가능.
  ```java
  public <T> T test(Supplier<T> supplier){
   System.out.println("supplier 인터페이스의 반환타입에 따라서 test 메소드의 반환타입이 결정됨");
  
   return supplier.get();
  }
  ```
- 동시에 여러 타입을 선언 가능 (멀티 타입 파라미터)
  - 제네릭 파라미터를 정의하는 곳에 `,`를 사용해 여러 타입을 선언할 수 있음.
  ```java
  class TestMap<T1, T2> implements Map<T1, T2>{
    
  }
  ```
- 와일드 카드를 이용하여 타입에 대하여 유연한 처리 가능
- 제네릭 선언 및 정의시에 타입의 상속관계 지정 가능

### 제네릭의 장점
- 클래스나 메소드 내부에서 사용되는 객체의 타입 안정성을 높일 수 있음
  - 타입 안정성<br>: 의도하지 않은 타입의 객체가 저장되는 것을 막고, 저장된 객체를 꺼내올 때 원래의 타입과 다른 타입으로 잘못 형변환되어 발생할 수 있는 오류를 줄여준다는 뜻.
- 반환값에 대한 타입 변환 및 타입 검사에 들어가는 노력을 줄일 수 있음.
- 타입을 유연하게 처리하며, 런타임 시 발생할 수 있는 타입에러를 컴파일 전에 검출할 수 있음
  - 즉, 타입에 대한 유연성과 안정성을 확보

[참고 문헌 1](http://www.tcpschool.com/java/java_generic_concept)<br>
[참고 문헌 2](https://jehuipark.github.io/java/java-generic)