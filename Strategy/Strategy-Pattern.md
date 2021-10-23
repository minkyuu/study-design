## 1. "What" is Strategy Pattern?

>: 행동 패턴 중 하나로 클래스의 행동 or 알고리즘을 실행 중에(at Runtime) 변경시킬 수 있는 패턴  
> (A class behavior or its algorithm can be changed at Runtime.)

<br>

>: 유사한 행위들을 캡슐화하여 객체의 행위를 바꾸고 싶은 경우 -> 직접 변경하는 것이 아닌 전략만 변경하여 유연하게 확장하는 패턴

<br>


### < Strategy Pattern Model >

![전략 패턴 모델](https://media.vlpt.us/images/y_dragonrise/post/01b02920-5e7d-4a90-b5be-7cdfe0f6091d/image.png)


<details>
<summary>각 요소에 대한 설명</summary>
<div markdown="1">
  
### 1. Context 😎

* 전략 패턴을 이용하는 역할
  
* 필요에 따라 동적으로 구체적인 전략을 바꿀 수 있도록 setter 메서드을 제공합니다.
  
### 2. Strategy 🛠

* 인터페이스 or 추상 클래스로 외부에서 동일한 방식으로 알고리즘을 호출하는 방법을 명시합니다.
 
* 요거를 통해서 전략을 쉽게 변경할 수 있습니다.
  
### 3. ConcreteStrategy ⛏🔧⚒

* 전략 패턴에서 명시한 알고리즘을 실제로 구현한 클래스

</div>
</details>

<br><br>

## 2. "Why" Strategy Pattern?

1. 코드를 수정하지 않고 다른 전략으로 변경할 수 있다.

    >: OCP를 준수함으로써 유지보수가 쉽고 확장성이 높아진다.

2. 코드 재사용

    >: 동일한 Strategy가 필요한 여러 Context들이 해당 Strategy를 재사용할 수 있다.

<br><br>

## 3. "How" to apply Strategy Pattern?

<details>
<summary>Answer (열기 전에 잠시 생각을 해봅시다!)</summary>
<div markdown="1">

1. Context, ConcreteStrategy (구체적으로 사용할 전략)를 만듭니다.

2. ConcreteStrategy의 전략 메서드를 각각의 전략에 맞게 구현합니다.

> 여기까지가 일반적인 전략 패턴을 사용하지 않은 상황이라고 볼 수 있겠습니다.

<br>


3. Strategy(인터페이스)를 통해서 ConcreteStrategy를 캡슐화합니다.

4. Context는 캡슐화하였던 Strategy(인터페이스)를 의존 주입을 받을 수 있도록 선언합니다.

5. 의존 주입은 Context의 setter 메서드를 통해서 이루어집니다.

</div>
</details>
    
<br><br>

## 4. SOLID 관점에서 보는 Strategy Pattern

* OCP 준수

>: 새로운 전략 클래스(ConcreteStrategy) 추가 시, 기존의 코드에 영향을 주지 않습니다.

* DIP 준수

>: 실질적인 전략 클래스가 아닌 캡슐화했던 인터페이스(Strategy)와 의존 관계를 갖습니다.

<br><br>

## 5. Strategy Pattern의 활용

* 로직 테스트, Mock 객체를 생성하여 Controller 테스트

* 이외에도 굉장히 많은 곳에서 사용할 수 있는 패턴!!!!!!!!!

<br><br>

## 6. Strategy Pattern을 마치면서

<br>

Q. Strategy Pattern을 학습해보시면서 무엇을 느끼셨나요??


<br>

---

내용 출처

1. https://velog.io/@y_dragonrise/%EB%94%94%EC%9E%90%EC%9D%B8-%ED%8C%A8%ED%84%B4-%EC%A0%84%EB%9E%B5-%ED%8C%A8%ED%84%B4Strategy-Pattern

2. https://im-yeobi.io/posts/design-pattern/strategy-pattern/

3. https://www.tutorialspoint.com/design_pattern/strategy_pattern.htm

4. https://velog.io/@kyle/%EB%94%94%EC%9E%90%EC%9D%B8-%ED%8C%A8%ED%84%B4-%EC%A0%84%EB%9E%B5%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80
