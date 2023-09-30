## [Java] Record가 무엇인가요?

### 개념 
- Java 자바 16에서 새로 도입된 기능으로 간단한 데이터 저장용 클래스를 정의하는데 더 간결하고 가독성 있게 작성할 수 있다. 데이터 클래스를 다룰 때 자주 사용되는 생성자, equals(), hashCode(), 그리고 toString() 메서드를 자동으로 생성하는 기능을 제공합니다. 이를 통해 간단하고 안전한 방식으로 데이터를 관리하고 처리할 수 있도록 돕는다. 이러한 특징들은 코드의 가독성을 높이고 버그를 줄이는 데 도움을 준다.

###  사용방법
``` java
  public record Gundam(String name, String pilot, String series) {}
```

### record 특징

- record는 불변 객체로 abstract로 선언할 수 없으며 암시적으로 final로 선언 된다. 한 번 값이 정해지면 setter를 통해 값을 변경할 수 없으며 상속을 할 수 없다. 즉, 레코드의 필드는 불변(immutable)한다.
- record 내 각 필드(헤더에 나열한 컴포넌트)는 private final로 정의된다. 따라서 명시적으로 접근 제어자를 선언하지 않아도 된다.
- 다른 클래스를 상속 받을 수 없습니다만, 인터페이스로는 구현이 가능하다. (extends : X, implements : O)
- 레코드 내부에 멤버 변수(인스턴스 필드)를 선언할 수 없다. 그러나 static 변수는 생성이 가능하다. 이는 헤더에서 정의한 멤버만을 record에서 관리하기 위함이다.


### 예제
```java
public record Person(String name, int age) {
    public static int totalCount; // 정적 멤버 변수 선언은 가능하다
}

public static class Main {
    public static void main(String[] args) {
        // 레코드를 생성하고 사용하는 예제
        Person person = new Person("Alice", 30);
        System.out.println(person.name()); // "Alice"
        System.out.println(person.age());  // 30   

        // 패턴 매칭을 사용하여 레코드의 필드 값을 추출
        if (person instanceof Person p) {
            System.out.println("Name: " + p.name()); //Name: Alice
            System.out.println("Age: " + p.age()); // Age: 30
        }
    }
}
```


참고 : [[Java]자바 record를 entity로?](https://velog.io/@power0080/java%EC%9E%90%EB%B0%94-record%EB%A5%BC-entity%EB%A1%9C)