# 자바&OOP

<Br>

##### **자바언어의 특징**

- 운영체제에 독립적이다. JVM을 사용하여 독립적으로 개발하여 모든 운영체제에서 사용할 수 있도록 변환시킬 수 있다.

- 객체 지향 언어이다. 상속, 캡슐화, 다형성이 잘 적용되어 사용할 수 있다. 그래서 재사용성, 생산성 향상, 자연적인 모델링, 유지보수가 우수하다.

- 자동 메모리 관리, GC가 자동적으로 메모리를 관리해 주기 때문에 메모리 관리 걱정을 할 필요가 없다.

- 멀티스레드(Multi-thread)를 지원한다.

 <Br>

##### **OOP 객체지향프로그래밍**

 구성하는 요소들을 객체로 바라보고, 객체들을 유기적으로 연결하여 프로그래밍 하는 것

 <Br>

##### **OOP 5대원칙 (SOLID)**

- SRP (Single Responsibility Principle)

단일 책임 원칙, 객체는 단 하나의 책임만 가져야 한다.

- OCP (Open Closed Principle)

개방 폐쇄 원칙, 기존의 코드를 변경하지 않으면서 기능을 추가할 수 있도록 설계 되어야 한다.

- LSP (Liskov substitution Principle)

리스코프 치환 원칙, 일반화 관계에 대한 이야기며, 자식 클래스는 최소한 자신의 부모 클래스에서 가능한 행위는 수행할 수 있어야 한다.

- ISP (Interface Segregation Principle)

인터페이스 분리 원칙, 자신이 사용하지 않는 인터페이스는 구현하지 말아야 한다.

- DIP (Dependency Inversion Principle)

상위 모듈은 하위 모듈에 종속되어서는 안된다. 둘다 추상화에 의존해야 한다. 추상화는 세부사항에 의존하지 않는다. 세부사항은 추상화에 의해 달라져야 한다.

[더 자세히 알기](https://blog.naver.com/11tjdnfeo/222102619581)

 <Br>

##### **캡슐화**

 객체의 속성과 행위를 하나로 묶고, 실제 구현 내용 일부를 외부에 감추어 은닉한다. getter/setter를 활용한 예제들

 <Br>

##### **추상화**

 공통적으로 가지는 특성이 있다면 추상화하고 상속받은 클래스들이 해당 함수를 구현하도록 하는 설계

 <Br>

##### **다형성**

동일한 메서드를 어떤 객체에 의해서 사용 되냐에 따라 다르게 동작하는 것, 오버라이딩 오버로딩

######  **오버로딩 오버라이딩**

- 오버로딩

  메소드 다중정의(같은 이름의 메소드를 한 클래스 내에서 여러 개 정의)

- 오버라이딩

  메소드 재정의(상의 클래스의 메소드를 상속받은 하위 클래스에서 다시 정의)

  <Br>

##### **상속**

Child c = new Parent(); 오류

Parent p = new Child(); 가능

 부모꺼는 자식꺼 이다.

 <Br>

##### **JVM이란?**

  자바를 실행하기 위한 가상머신이다. 일반 언어들은 바로 os를 거쳐 하드웨어로 전달되지만, 자바 언어는 jvm을 거쳐 해석된 후 os를 거쳐 하드웨어로 전달된다. 자바 코드에서 컴파일을 하면 바이트 코드로 변환되고, 이를 각 os에 맞게 jvm을 이용하여 실행한다. 이 때문에 다른 언어보다 속도가 느릴 수 있지만, 요즘 하드웨어의 성능이 좋아지면서 속도의 격차가 줄었다.

 <Br>

##### **JVM 구성**

![jvm](https://github.com/ssyup4259/interview/blob/master/img/jvm.png?raw=true)

1. 클래스 로더

     자바는 동적으로 클래스를 읽어오므로, 프로그램이 실행 중인 런타임에서야 모든 코드가 자바 가상 머신과 연결된다. 이렇게 동적으로 클래스를 로딩해주는 역할

2. Excution Engine

     명령어 단위로 실행하는 역할, 여기에는 인터프리터 방식과 JIT(Just In Time) 컴파일러를 이용하는 방식이 있다.

   - 인터프리터는 명령어를 한줄씩 해석해서 하나하나 실행한다. 속도가 느리다

   - JIT 컴파일러란 프로그램이 실행 중인 런타임에 실제 기계어로 변환해 주는 컴파일러

3. 가비지 컬렉터

   gc는 더는 사용하지 않는 메모리를 자동으로 회수

4. Runtime Data Area

   method, heap, stack, pc register, Native Method Stack 5가지로 구분할 수 있다. 자바 에서 스레드 들은 메서드와 힙 영역을 공유한다. 스택영역은 공유 불가능하다.

   - 메서드(Method) 영역: 클래스에 대한 정보를 저장(클래스 변수 포함), static 키워드가 붙은 것들이 저장, Constant Pool(상수 풀: 문자 상수, 타입, 필드, 객체 참조) 가 저장됨, 가장 먼저 로딩되고 프로그램 종료시까지 남아 있다.
   - 힙(Heap) 영역 : 프로그램 중 실행 생성되는 인스턴스, 인스턴스 변수들이 생성되는 곳(new 로 생성 되는 것들), 메소드 영역에 로드된 클래스만 생성이 가능하다. GC가 상주하는 곳
   - 콜 스택(Stack) : execution stack 이기도 함 메소드가 작업을 수행하는 동안 지역변수 들과 연산의 중간 결과 등을 저장하는데 사용 메소드가 작업을 끝내면 할당 되었던 메모리 공간은 반환됨
   - PC Register : 현재 실행되는 부분의 명령과 주소를 저장
   - Native method stack : 자바 외의 다른 언어에서 제공되는 메서드들이 저장되는 공간

[더 자세히 알기](https://blog.naver.com/11tjdnfeo/222102621259)

<Br>

##### **클래스 변수 vs 인스턴스 변수 vs 지역**

```java
class Info{
    String name;  -> 인스턴스 변수
    static int num; -> 클래스 변수
        
    void method() {
        int age; -> 지역(local) 변수
    }
}
```

  클래스 변수는 모든 인스턴스가 하나의 저장공간을 공유하므로 공통된 값을 가지고, 인스턴스 변수는 인스턴스가 생성될 때 마다 생성되므로 각기 다른 값을 유지 할 수 있다.

<Br>

#####  JRE이란?

java runtime environment, jvm이 실행하는 것을 도와주는 조력자 역할, 자바 실행 환경

 <Br>

##### **JDK이란?**

 java development kit, 개발자를 위한 환경, jre을 통해 실행 환경을 구축하고 jvm을 통해 실행을 할수 있고, jdk를 통해서 개발을 할 수 있다. .java 파일을 컴파일 하여 바이트코드(.class)를 생성하는 단계까지 제공(javac)

 <Br>

##### **JDK 버전 별 차이**

1.5 : 확장 for문 사용 가능, 제네릭 추가, 오토박싱, 오토언박싱 추가

1.7 : switch 문 조건 문자열 가능

1.8 : Oracle 인수 후 첫 버전, 람다식 추가

 <Br>

##### **GC(Garbage Collection)이란?**

사용하지 않는 메모리를 정리하기 위한 기능이다. 메모리 구역을 나누어 GC를 진행시킨다. gc는 힙에 상주

 ![gc](https://github.com/ssyup4259/interview/blob/master/img/gc.gif?raw=true)

  메모리에 객체가 처음 생성되면 ,eden 영역에 객체가 지정된다. eden 영역에 데이터가 어느정도 쌓이게 된다면 어디론가 옮겨지거(promotion)나 삭제된다(minor gc). 이때 옮겨가는 위치가 survivor 영역, 두개의 survivor 영역이 있는데 하나는 반드시 비워 둬야 한다. 할당된 Survivor 영역이 차면 Eden 영역에 있는 객체와 꽉 찬 Survivor 영역에 있는 객체가 비어 있는 Survivor 영역으로 이동합니다. 그러다가 더 큰 객체가 생성되거나, 더 이상 Young 영역에 공간이 남지 않으면 객체들은 Old 영역으로 이동하게 됩니다. major 는 Old 영역에서 객체가 정리되는 것을 말한다.

  Stop-the-world, GC를 실행하기 위해 JVM이 어플리케이션 실행을 멈추는 것, GC를 실행하는 스레드를 제외한 나머지 스레드는 모두 작업을 멈춘다. gc를 튜닝한다는 말은 stop-the-world 시간을 줄이는 것이다.

[더 자세히 알기](https://blog.naver.com/11tjdnfeo/222102622375) 

<Br>

##### **클래스와 객체**

- 클래스 : 현실 세계의 물건의 속성과 동작을 추려내 필드와 메서드로 정의한 것으로 아직 메모리가 할당되지 않은 상태이다.

- 객체 : 이 클래스라는 설계도를 기반으로 실제 메모리가 잡힌 것을 의미한다. 

 <Br>

##### **접근 지정자**

![public](https://github.com/ssyup4259/interview/blob/master/img/public.png?raw=true)

- private : 같은 클래스 내에서만

- (default) : 같은 클래스, 같은 패키지 내에서만

- protected : 패키지가 다를 경우에는 상속 받았을때만

- public : 어디서나

 <Br>

##### **Call by Value, Call by Reference**

CBV : 값에 의한 참조

CBR : 주소에 의한 참조

 <Br>

##### **String, StringBuilder, StringBuffer**

- String 

    String 클래스는 Immutable 객체이기에 +등 concat 연산시 원본을 변경하지 않고 새로운 String 인스턴스를 생성 해야한다. 기존 String 객체가 있고 연산 된후의 객체가 생기는 것이다. jdk1.5 부터는 컴파일 단계에서 String 객체를 사용하더라도 StringBuilder로 컴파일 되도록 변경되었으나 여전히 반복루프 안에서 연산시 새로운 객체를 계속추가한다.

- StringBuilder

    연산이 많은 경우 사용하는것이 좋다. 동기화 처리를 안해줘도 되서 StringBuffer 보다 빠르다.

- StringBuffer

    Thread-safe하다. 멀티 스레드 환경에서 동기화의 지원 여부가 다른다. 모든 메소드에 대해 synchronized 키워드가 붙어있다.

 <Br>

##### **equals와 ==의 차이**

  Object의 경우 차이가 없다. 메소드를 자세히 살펴보면 return(this==obj) 이기 때문, 그러나 String의 equals를 오버라이드 하면 if(this==obj) 이후 if( obj instanceof str)이 나온다. 따라서 == 주소 값 비교, equals는 1차적으로 주소 값 비교, 2차적으로 값 비교

 <Br>

##### **추상클래스 인터페이스의 차이**

- 추상클래스

    실제 클래스의 공통적인 부분을 추출해 규격을 잡아 놓은 클래스이다. 추상클래스의 객체는 미완성의 클래스 이므로 생성 불가능, 상속을 통해서 자손클래스에 의해서 완성할 수 있다. 새로운 클래스를 작성하는데 바탕이 된다. (extends)

    다른 클래스에서 추상 클래스를 상속하려면 미완의 메소드를 구현해야 한다. 추상 클래스 안에는 구현 메소드와 추상 메소드 둘 다 만들 수 있다.

- 인터페이스

    인터페이스는 추상화 정도가 추상클래스보다 높다 클래스 안 모든 메소드가 추상 메소드이다. 구현을 강제한다. 메소드에 abstract 안 써도 된다. 인터페이스는 다중 상속을 지원한다. (implements)

 <Br>

##### **Comparable vs Comparator**

- Comparable : 기본 정렬 기준을 구현하는데 사용 (compareTo)

- Comparator : 기본 정렬 기준 외에 다른 기준으로 정렬하고자 할 때 사용(compare)

<Br>

##### **Collection**

ArrayList, LinkedList, Vector, HashSet, TreeSet, HashMap, TreeMap 등이 있다.

|           | List                          | Set              | Map                |
| --------- | ----------------------------- | ---------------- | ------------------ |
| data 순서 | O                             | X                | X                  |
| 중복      | O                             | X                | X                  |
| 종류      | vector, arraylist, linkedlist | hashset, treeset | hashtable, hashmap |

Tree 가 들어가는 것은 이진 검색 트리 또는레드 블랙 트리라는 자료구조의 형태로 데이터 저장한다.

멀티 스레드 환경에서 vector와 hashtable은 thread safe 하다

 <Br>

##### **Array, ArrayList, LinkedList**

- Array

    Array는 메모리에 한번 할당 되면 길이가 고정 되어 있기에 그것을 계속 사용 조금 더 빠르다.

- ArrayList

    검색에 유리한 구조, 내부적으로 데이터를 배열에서 관리한다. 추가 삭제를 수행 할 시 임시 배열을 생성해 복사하는 방법을 사용한다. 인덱스를 가지고 있기에 한번에 참조 가능.

- LinkedList

    데이터를 저장하는 각 노드에 값과 다음 노드의 주소를 가지고 있다. 추가시 링크만 연결해서 새로 추가하고 삭제시 링크만 삭제하면 되서 성능이 좋다. 검색시는 인덱스가 없어 처음부터 노드를 순회해야한다.

<Br>

##### **쓰레드 구현**

1. Thread 클래스를 상속,

2. Runnable인터페이스 구현

 <Br>

##### **업캐스팅 vs 다운 캐스팅**

- Parent p = new Child() -> 업 캐스팅

- Child c = (Child)p -> 다운 캐스팅

 <Br>

##### **Wrapper 클래스**

8종류의 기본형을 클래스로 만들기 위해 존재

언박싱 : 참조형 -> 기본형

오토박싱 : 기본형 -> 참조형

 <Br>

##### **Generic**

자료형을 정하지 않고 여러가지 타입을 한번에 사용하는 방식

```java
public class GenericTest<T> {
    private T data;
    
    public T getData() {
    	return data;
    }
    
    public void setData(T data){
    	this.data = data;
    }
}
```

<Br>

##### **람다식**

메서드를 하나의 식으로 표현한 것, 람다식을 통해 메서드가 하나의 독립적인 기능을 하기 때문에 함수라는 용어를 사용한다. 객체지향언어인 동시에 함수형 언어행위를 할 수 있다.

```java
(int a, int b) -> {return a>b ? a: b;}
```

