## 람다

- 메서드를 하나의 식으로 표현한 것으로 `함수형 인터페이스를 구현한 익명 객체`입니다.

```java
/*
기존: 반환타입 메서드이름 (매개변수) {}   
=====>   
변경: (매개변수) -> { }
*/

// 예시1
int max(int a,int b){return a<b ?b:a};
// ====> 
    (int a,int b)->return a<b ?b:a;

// 예시2
    Comparator<Apple> byWeight=new Comparator<Apple>(){
@Override
public int compare(Apple a1,Apple a2){
    return a1.getWeight().compareTo(a2.getWeight());
    }
    };
// ====>
    Comparator<Apple> byWeight=
    (Apple a1,Apple a2)->a1.getWeight().compareTo(a2.getWeight());
```

### 특징

- java.util.function 패키지에는 자주 사용하는 다양한 함수형 인터페이스가 정의되어 있습니다.

```java
    Predicate<T> :T->boolean
    Consumer<T> :T->void
    Function<T, R> :T->R
    Supplier<T> :()->T
    UnaryOperator<T> :T->T
    BinaryOperator<T> :(T,T)->T
```

## 스트림

- 스트림은 데이터 처리 연산를 표준화된 방법으로 수행하기 위한 `자바8의 새로운 API`입니다.

### 특징

1. 스트림은 데이터 소스를 변경하지 않고 읽기만 지원합니다.
2. 스트림은 일회용으로써 재사용할 수 없습니다.
3. 스트림은 작업을 내부 반복으로 처리합니다.
4. 스트림은 중간 연산과 최종 연산으로 구분되는데 최종 연산이 수행되기 전까지 중간 연산이 수행되지 않습니다.

```java
// 기본
List<Dish> lowCaloricDishes = new ArrayList<>();
for(Dish d:dishes){
    if(d.getCalories()< 400){
        lowCaloricDishes.add(d);
    }
}

List<String> lowCaloricDishesName=new ArrayList<>();
Collections.sort(lowCaloricDishes,new Comparator<Dish>(){
    // 익명 클래스로 요리 정렬
    @Override
    public int compare(Dish d1,Dish d2){
        return Integer.compare(d1.getCalories(),d2.getCalories());
    }
});
    
for(Dish d:lowCaloricDishes){ // 정렬된 리스트를 처리하면서 요리 이름 선택
    lowCaloricDishesName.add(d.getName());
}

// 스트림
    List<String> lowCaloridDishesName=
    menu.stream()
    .filter(d->d.getCalories()< 400) // 400칼로리 이하의 요리 선택
    .sorted(comparing(Dish::getCalories)) // 칼로리로 요리 정렬
    .map(Dish::getName) // 요리명 추출
    .collect(toList()); // 모든 요리명을 리스트에 저장
```