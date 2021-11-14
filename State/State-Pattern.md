## 1. "What" is State Pattern? 😮
* 객체 자신의 **"내부 상태에 따라"** 객체의 행위를 변경할 수 있도록 하는 패턴

<br>

## 2. "Why" we use State Pattern? 🤔

### State Pattern을 사용하지 않을 경우

* if ~ else , switch 조건문을 사용하게 되는데, 이런 구조는 상태 테이블을 변화시키거나 새로운 상태를 추가하는 것이 쉽지 않습니다.
  
    > (새로운 상태를 추가할 때, 많은 메서드를 변경해주어야 합니다.)

<br>

### State Pattern의 장점

1. 새로운 상태가 추가되더라도 Context 코드가 받는 영향은 최소화

2. 클래스를 추가하더라도 기존의 메서드의 코드는 그대로 유지

3. 한 상태에 따른 동작을 구현한 코드가 상태별로 구분되기 때문에 상태별 동작을 수정하기 쉽다

<br>

## 3. "How" to apply State Pattern? 🧐

![State Pattern UML](https://media.vlpt.us/images/y_dragonrise/post/b0cd2535-b0f8-4aa6-8fdc-7c1c164e89b2/image.png)

1. State 설계
    * Concrete State 정의
    
    * State (interface)로 Concrete State들을 캡슐화하기

2. Context와 State (interface) 사이에 의존 관계 생성
    
    * Context에 State를 의존 주입하는 방식으로 관계를 생성 (아래의 3과 연결됩니다)
    
3. Context에서 동적으로 상태가 변화시킬 수 있도록 setter 메서드 생성, state 호출 메서드 생성

<br>


## 4. State Pattern 활용 🛠

* 객체의 행동이 상태에 따라 변화가 필요한 경우 활용

  > 즉, 객체의 상태에 따라 런타임에 행동이 바뀌어야 하는 경우


<br>

## 5. SOLID 관점에서 본 State Pattern

* OCP 준수

>: 새로운 상태 추가 시, 기존의 코드에 영향을 주지 않습니다.

* DIP 준수

>: Concrete State 클래스가 아닌 인터페이스 State와 의존 관계를 갖습니다.

<br>


## 6. 생각해보기! 🤔

Q. State Pattern vs Strategy Pattern , 두 패턴은 어떻게 다른 것일까요??

[참고 내용](https://github.com/KWSStudy/Refactoring/issues/2) 

<br>

<details>
<summary>두 패턴의 UML 비교</summary>
<div markdown="1">
  
<br>
  
### Strategy Pattern UML

![Strategy Pattern](https://media.vlpt.us/images/y_dragonrise/post/01b02920-5e7d-4a90-b5be-7cdfe0f6091d/image.png)

<br>
  
### State Pattern UML

![State Pattern UML](https://media.vlpt.us/images/y_dragonrise/post/b0cd2535-b0f8-4aa6-8fdc-7c1c164e89b2/image.png)

</div>
</details>
  
<br>

## 7. State Pattern을 마치면서 

Q. State Pattern을 학습하시면서 어떤 것을 느끼셨나요?

<br>

---
참조 내용 출처

1. https://victorydntmd.tistory.com/294

2. https://kscory.com/dev/design-pattern/state

3. https://always-intern.tistory.com/9

4. https://tecoble.techcourse.co.kr/post/2021-04-26-state-pattern/
