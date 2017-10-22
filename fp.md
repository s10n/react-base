## 용어 정의

### [Pure function](https://en.wikipedia.org/wiki/Pure_function)
1. The function always evaluates the same result value given the same argument value(s). The function result value cannot depend on any hidden information or state that may change while program execution proceeds or between different executions of the program, nor can it depend on any external input from I/O devices.
2. Evaluation of the result does not cause any semantically observable side effect or output, such as mutation of mutable objects or output to I/O devices.

### [Referential transparency](https://en.wikipedia.org/wiki/Referential_transparency)
An expression is said to be referentially transparent if it can be replaced with its corresponding value without changing the program's behavior.

### [Side-effect](https://en.wikipedia.org/wiki/Side_effect_(computer_science))
In computer science, a function or expression is said to have a side effect if it modifies some state outside its scope or has an observable interaction with its calling functions or the outside world besides returning a value. For example, a particular function might modify a global variable or static variable, modify one of its arguments, raise an exception, write data to a display or file, read data, or call other side-effecting functions.

Side effects are the most common way that a program interacts with the outside world (people, filesystems, other computers on networks).

### [Thread safety](https://en.wikipedia.org/wiki/Thread_safety)
Thread-safe code only manipulates shared data structures in a manner that ensures that all threads behave properly and fulfil their design specifications without unintended interaction.

스레드 안전은 멀티 스레드 프로그래밍에서 일반적으로 어떤 함수나 변수, 혹은 객체가 여러 스레드로부터 동시에 접근이 이루어져도 프로그램의 실행에 문제가 없음을 뜻한다. 보다 엄밀하게는 하나의 함수가 한 스레드로부터 호출되어 실행 중일 때, 다른 스레드가 그 함수를 호출하여 동시에 함께 실행되더라도 각 스레드에서의 함수의 수행 결과가 올바로 나오는 것으로 정의한다.

### [Assignment](https://en.wikipedia.org/wiki/Assignment_(computer_science))
In computer programming, an assignment statement sets and/or re-sets the value stored in the storage location(s) denoted by a variable name; in other words, it copies a value into the variable.


## 함수형 프로그래밍

### [Functional programming](https://en.wikipedia.org/wiki/Functional_programming)
Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

> Functional programming is programming without assignment statements.

### 규칙
* 순수 함수를 작성한다.

### 장점
* 부작용을 제거하면 프로그램의 동작을 이해하고 예측하기가 훨씬 쉽게 된다. 이것이 함수형 프로그래밍으로 개발하려는 핵심 동기중 하나이다.
  - 테스트, 디버깅, 가독성, 유지보수
  - 참조 투명성으로 인해 (치환을 통해) 동작을 추론하기 쉽다.

### 순수 함수의 장점
* 스레드 안전하고, 병렬적인 계산이 가능하다.
  - 성능 향상: 멀티코어 환경에서 동시성 처리

### 부작용의 예시
```java
public Program getCurrentProgram(TVGuide guide, int channel) {
  Schedule schedule = guide.getSchedule(channel);

  Program current = schedule.programAt(new Date());

  return current;
}
```
```java
public Program getProgramAt(TVGuide guide, int channel, Date when) {
  Schedule schedule = guide.getSchedule(channel);

  Program program = schedule.programAt(when);

  return program;
}
```

It’s vastly easier to test. Testing different times of day, clock changes, leap years, will all be straightforward, because we can pass in any time we like. I’ve seen code like the first version in production, with all sorts of clever tricks to spoof the current system clock for testing’s sake. Imagine the effort, when we can just make it a parameter!

(And as an aside, it’s also more useful. We get, “what program starts in an hour?” code for free.)

출처: [What Is Functional Programming? - Kris Jenkins](http://blog.jenkster.com/2015/12/what-is-functional-programming.html) ([번역](https://medium.com/@jooyunghan/함수형-프로그래밍이란-무엇인가-fab4e960d263))

### 더 알아보기
* Immutable.js(Facebook) - Trie data structure (Structural sharing)
* Memoization
* Module reusability, Composition
* Race condition - 세마포어와 락
