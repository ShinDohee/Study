# Part1 기초 

## Chapter 1. 자바 8, 9, 10 ,11 : 무슨 일이 일어나고 있는가 ?

- 자바가 거듭 변화하는 이유
- 컴퓨팅 환경의 변화 
- 자바에 부여되는 시대적 변화 요구
- 바자 8과 자바 9의 새로운 핵심 기능 소개 

### 1.1 역사의 흐름은 무엇인가 ?

자바 8은 갈결한 코드, 멀티코어 프로세서의 쉬운 활용이라는 두가지 요구사항을 기반으로 한다. 

> 자바8에서 제공하는 새로운 기술(가장 대표적)
>
> * 스트림 API
> * 매서드에 코드 전달하는 기법
>   * 인터페스의 디폴트 메서드

자바 8 기법은 함수형 프로그래밍에서 위력을 발휘 한다. 

### 1.2 왜 아직도 자바는 변화하는가?

#### 1.2.1 프로그래밍 언어 생태계에서 자바의 위치

#### 1.2.2 스트림처리

- 스트림이란 ?  한번에 한개씩 만들어지는 연속적인 테이터 항목들의 모임 

- 자바 8에는 java.util.stream 패키지에 스트림 API 가 추가 되었다. 스트림 패키지에 정의된 STream<T> 는 T형식으로 구성된 일련의 항목을 의미한다. 

- 스트림 API의 핵심은 기존에는 한 번에 한 항목을 처리했지만, 이제 자바 8에서는 우리가 하려는 작업을(데이터베이스의 질의처럼) 고수준으로 추상화해서 일련의 스트림으로 만들어 처리 할 수 있다는 것이다. 

- 스트림 파이트 파린을 이요해서 입력 부분을 여러 cPU 코어에 쉽게 할당 할 수있다는 부가적인 이득도 얻을 수 있다. 

- 스레드라는 복잡한 작업을 사용하지 않으면서도 공짜로 병렬성을 얻을 수도 있다. 

#### 1.2.3 동작 파라미터화로 메서드에 코드 전달하기

- 코드의 일부를 API로 전달하는 기능이  추가되었다. 
- 이러한 기능은 동작 파라미터화라고 부른다.  이는 스트림 API는 연산의 동작을 파라미터화 할 수 있는 코드를 전달한다는 사상에 기초하기 때문에 중요하다. 

#### 1.2.4 병렬성과 공유 가변 데이터 

#### 1.2.5 자바가 진화해야하는 이유

### 1.3 자바 함수

프로그래밍 언어에서 함수라는 용어는 매서드, 특히 정적메서드와 같은 의미로 사용되며, 이에 더해 수학적인 함수처럼 사용되며 부작용을 일으키지 않는 함수를 의미함

#### 1.3.1 매서드와 람다를 일급 시민으로 

 메서드 참조(::)- 기존에  비해 문제 자체를 더 직접적으로 설명한다는 점이 자바 8 코드의 장점 

* 람다: 익명 함수 : 함수도 값으로 취급 할 수 있다.

#### 1.3.2 코드 넘겨주기

#### 1.3.3 메서드 전달에서 람다로    

### 1.4 스트림

스트림 API는 컬렉션 API 와 상당히 다른 방식으로 데이터를 처리함

- 컬렉션에서는 for-each 루프를 이용해서 각 요소를 반복하면서 작업을 수행 한다. (외부반복)
- 스트림 API는 라이브러리 내부에서 모든 데이터를 처리한다 (내부반봅)

#### 1.4.1 멀티스레딩은 어렵다 

컬렉션을 처리하면서 발생하는 모호함과 반복적인 코드 문제, 멀티코어 활용의 어려움이라는 두가지 문제 해결 

- 컬렉션은 어떻게 데이터를 저장하고 접근할 지에 중점을 두는 반면, 스트림은 데이터에 어떤 계싼을 할것인지 묘사하는것에 중점을 둔다. 
- 스트림은 스트림 내의 요소를 쉽게 병렬로 처리할 수 있는 환경을 제공한다는 것이 핵심!

### 1.5 디폴트 메서드와 자바 모듈

### 1.6 함수형 프로그래밍에서 가져온 다른 유용한 아이디어

### 1.7 마치며 

- 자바8 은 프로그램을 더 효과적이고 간결하게 구현 할 수 있는 새로운 개념과 기능을 제공
- 기존의 자바프로그래밍 기법으로는 멀티코어의 프로세서를 온전히 활용하기 어려움
- 함수는 일긊값, 메서드를 어떻게 함수형 값으로 넘겨주는지, 익명함수(람다)를 어떻게 구현하는지 기억 할 것
- 스트림 개념 중 일부는 컬렉션에서 가져온 것, 스트림과 컬랙션을 적절하게 활용하면 스트림의 인수를 병렬로 처리 할 수 있으면 가독성이 좋은 코드 구현 가능
- 함수형 프로그래밍에서 null 처리 방법과 패턴 매칭 활용 방법등 흥미로운 기법을 발견



## Chapter2. 동작 파라미터화 코드 전달하기

- 변화하는 요구사항에 대응
- 동작 파라미터화
- 익명클래스
- 람다 표현식

### 2.1 변화하는 요구에 대응하기 

#### 	2.1.1 첫번째 시도 : 녹색 사과 필터링

```java
public static List<Apple> filterGreenApples(List<Apple> inventory) {
    List<Apple> result = new ArrayList<>();  <-- 사과 누적 리스트 
    for (Apple apple : inventory) {
      if (apple.getColor() == Color.GREEN) { <-- 녹색사과만 선택 
        result.add(apple);
      }
    }
    return result;
 }
```
​	=> 현재 코드는 녹색 사과만 필터링 하고 있지만, 추후에 좀더 다양한 색으로 필터링 하는 등의 변화에 적절하게 대응하기 어렵다. 

​		거의 비슷한 코드가 반복 존재 한다면, 그 코드를 추상화 하라

#### 	2.1.2 두번째 시도 :  색을 파라미터화

```java
public static List<Apple> filterApplesByColor(List<Apple> inventory, Color color) {
  List<Apple> result = new ArrayList<>();
  for (Apple apple : inventory) {
    if (apple.getColor() == color) {
      result.add(apple);
    }
  }
  return result;
}
```
=> 이후에 다른 조건들을 추가하게 된다면, 해당 조건에 대한 부분을 파라메터로 전달 한 메서드를 구현 하면 되겠지만, 좋은 해결책이 아니다.  코드의 중복이 많이 일어난다. . Don't repeat yourself (같은것을 반복하지 말것 ) 원칙을 어기게 된다. 

#### 	2.1.3 세번째 시도 :  가능한 모든 속성으로 필터링

​	모든 속성을 파라미터로 추가 하게 된다면, 추후에 요구사항이 바뀌었을때 유연하게 대응 할 수 없다. 

### 2.2 동작 파라미터화 

참 or 거짓을 반환하는 함수를 *프레디케이트*라고 한다. 선태조건을 결정하는 인터페이스를 정의하자. 조건에 따라 filter 메서드가 다르게 동작할 것이라고 예상할수 있다. 이를 전략디자인패턴 이라고 부른다. 

```java 
interface ApplePredicate { 

    boolean test(Apple a);

  }

  static class AppleWeightPredicate implements ApplePredicate {

    @Override
    public boolean test(Apple apple) {
      return apple.getWeight() > 150;
    }

  }

  static class AppleColorPredicate implements ApplePredicate {

    @Override
    public boolean test(Apple apple) {
      return apple.getColor() == Color.GREEN;
    }
  }
```


전략 디자인 패턴 : 각 알고리즈을 캡슐화하는 알고리즘 패밀리를 정희해 둔 다음에, 런타임에 알고리즘을 선택하는 기법

 ApplePredicate : 알고리즘 패밀리 // AppleColorPredicate,AppleWeightPredicate : 전략

ApplePredicate는 어떻게 다양한 동작을 수행 할 수 있을까 ?  filterApples에서 ApplePredicate 객체를 받아 애플의 조건을 검사하도록 메서드를 수정해야함. 

#### 	2.2.1 네번째 시도 : 추상적 조건으로 필터링

```java
public static List<Apple> filter(List<Apple> inventory, ApplePredicate p) {
  List<Apple> result = new ArrayList<>();
  for (Apple apple : inventory) {
    if (p.test(apple)) { // 프레디케이트 객체로 사과 점사조건을 캡슐화 하였음. 
      result.add(apple);
    }
  }
  return result;
}
```
1. 코드/동작 전달하기

2. 한개의 파라미터, 다양한 동작

   컬렉션 탐색 로직과 항목에 적용할 동작을 분리 할 수 있따는 것이 동작 파라미터의 강점이다. 

### 2.3 복잡한 과정 간소화

새로운 동작을 전달하려면 ApplePredicate 인터페이스를 구현하는 여러 클래스를 정의한 다음에, 인스터스화 해야한다. 이는 번거로운 작업이다. 

클래스 선언과 인스턴스화를 동시에 할 수 있는 익명 클래스 라는 기법을 활용하자.

#### 	2.3.1 익명클래스

​		익명 클래스란 ? 자바의 지역 클래스와 비슷한 개념, 이름이 없는 클래스이고 클래스 선언과 인스턴스화를 동시에 할 수 있다. 즉, 즉석에서 필요한 구현을 만들		어 사용 할 수 있다. 

#### 	2.3.2 다섯번째 시도 : 익명클래스 사용

```java
 List<Apple> redApples = filter(inventory, new ApplePredicate() { // filterApples 메서드의 종작을 직접 파라미터화 했다. 
   public boolean test(Apple a) {
     return RED.equlas(a.getColor());
   }
});
```
​	익명 클래스로도 부족한 점이 있다. 

	1. 여전히 많은 공간을 차지한다. 
 	2. 많은 프로그래머들이 익명클래스 사용에 익숙하지 않다. 

코드조각을 전달하는 과정에서 객체를 만들고 명시적으로 새로운 동작을 정의하는 메서드를 구현하는 점은 변하지 않는다.  

동작파라미터화를 이용하면서 요구사항 변화에 더 유연하게 대응할 수 있으므로 모든 프로그래머가 동작 파라미터화를 사용하도록 권장한다. 람다 표현식으로 써서 더 간단한 코드 전달기법을 도입해서 이 문제를 해결 하였음 보게 될것이다. 

#### 	2.3.3 여섯번째 시도 : 람다 표현식 사용

```java
 List<Apple> greenApples = filterApples(inventory, (Apple a) -> RED.equlas(a.getColor()));
```
#### 	2.3.4 일곱번째 시도 : 리스트 형식으로 추상화 

### 2.4 실전예제 

#### 	2.4.1 Comparatore 로 정렬하기 

```java
public interface Comparator<T> { 
   int compare(T o1, T o2);
}

inventory.sort(new Comparator<Apple>() {
	public int compare(Apple a1, Apple a2) {
		return a1.getWeight().compareTo(a2.getWeight());
		}
});

//람다 표현식
inventory.sort((Apple a1, Apple a2) -> a1.getWeight().compareTo(a2.getWeight()) );
```

#### 	2.4.2 Runnable로 코드 실행하기 

자바 스레드를 이용하면 병렬로 코드 블록을 실행 할 수 있다. 자바 8까지는 Thread 생성자에 객체만 전달 할 수 있으므로, 보통 겨로가를 반환하지 않는 void run 메소드를 포함하는 익명 클래스가 Runnable 인터페이스를 구현 하도록 하는 것이 일반 적인 방법인데. 

이제 Runnable 인터페이스를 이용해서 실행할코드 블록을 지정할 수 있다. 

```java
public interface Runnable { 
  void run();
}
Thread t = new Thread(new Runnable (){
    public void run(){
         System.out.println("Hello World");
    }
} );
//람다 표현식
    Thread T = new Thread( () ->  System.out.println("Hello World"));

```

#### 	2.4.3. Callable을 결과로 반환하기 

ExecutorService 인터페이스는 태스크 제출과 실행과정의 연관성을 끊어준다. 태스크를 스레드 풀로 보내고 결과를 Future로 저장할 수 있다는 점이 스레드와 Runnable을 이용하는 방식과는 다른점이다. 지금은 Callable  인터페이스를 통해 결과를 반환하는 태스크를 만든다는 사실만 알아두자! 

이는 Runnable의 업그레이드 버전이라고 생각 할 수 있다. 

```java
public interface Callable<V> { 
  V call();
}

ExecutorService executorService = ExecutorService.newChachedThreadPool();
Future<String> ThreadName = executorService.submit(new Callable<String>(){
    @Ovarride public String call() throws Exception{
        return Thread.currentThread().getName();
    }
});
//람다 표현식
Future<String> ThreadName = executorService.submit( () -> Thread.currentThread().getName());
```

#### 	2.4.4 GUI 이벤트 처리하기 

마우스 클릭이나 문자여 ㄹ위로 이동하는 등의 이벤트에 대응하는 동작을 수행하는 식으로동작한다. 

자바 FX 에서는 setOnAction 메서드에 EventHandler를 전달 함으로써 이벤트에 어떻게 설정할 수 있다. 

```java
Button button = new Button("Send");
button.setOnAction(new EventHandler<ActionEvent>(){
    public void handle(ActionEvent event){
        label.setText("sent!!!");
    }
});
//람다 표현식
button.setOnAction((ActionEvent event) -> label.setText("sent!!!"));
```

#### 

### 2.5 마치며 

- 동작 파라미터화에서는 메서드 내부적으로 다양한 동작을 수행 할 수 있도록 코드를 메스드 인수로 전달 

- 동작 파라메터화를 이용하면 변화하는 요구사항에 더 잘 대응 할 수 있는 코드를 구현 할 수 있으며, 추 후 엔지니어링 비용을 줄일 수 있음

- 코드 전달 기법을 이용하면 동작을 메서드의 인수로 전달 할 수 있다. 하지만 자바 8 이전에는 코드가 지저분하게 구현 되었지만 자바8에서는 인터페이스를 상속받아 여러 클래스를 구현해야하는수고를 없앨 수 잇는 방법을 제공

- 자바 API의 많은 메서드는 정렬, 스레드, GUI 처리등을 포함한 다양한 동작으로 파라미터화 시킴 

  
  
  