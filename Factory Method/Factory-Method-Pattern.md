## 1. "What" is the Factory Method Pattern? 🏭
* 생성 패턴 중 하나로, 객체 생성 처리를 서브 클래스에서 하도록 하는 패턴

  > 생성될 객체에 대한 결정은 서브 클래스(Concrete Factory) 쪽에서 내리는 패턴입니다

  > 즉, 인스턴스화에 대한 책임을 객체를 사용하는 클라이언트에서 팩토리 클래스로 가져옵니다

<br>

Q. 왜 서브 클래스에 책임을 넘긴 것인가요??

* 조건에 따라 or 상황에 따라 (동적으로) 각각 다른 객체를 생성하기 위해!

<br>

## 2. "Why" we use Factory Method Pattern? 🤔
 
Factory Method Pattern의 장점

- 팩토리 패턴은 클라이언트와 객체 생성 모듈 간 종속성을 낮추고, 결합도를 느슨하게 하며, 확장을 쉽게 할 수 있습니다.

  > 서브 클래스의 수정 혹은 삭제가 일어나더라도 클라이언트는 알 수 없기 때문에 코드를 변경할 필요가 없습니다.

<br>

- 팩토리 패턴은 클라이언트와 구현 객체들 사이에 추상화를 제공합니다.

  > 확장성 있는 전체 프로젝트 구성 가능


<br>

## 3. "How" to apply Factory Method Pattern? ⚒🛠

![Factory Method Pattern Diagram](https://www.oreilly.com/library/view/design-patterns-and/9781786463593/assets/7b9b05d9-b441-4fa4-a6f4-05bbda05524a.png)

1. 전체 구조 설계

2. Product, Concrete Product 정의

3. 추상화 레벨이 높은 클래스와 의존 관계 생성
 
4. 객체 생성 처리를 하는 서브 클래스 (Concrete Factory)에 메서드를 구현합니다

<br> 

<details>
<summary> 잠깐 생각해보기! </summary>
<div markdown="1">

<br>

> Q1. If문 vs Switch문 성능 비교해보기!


> Q2. Template Method Pattern 예제에 적용?

</div>
</details>

<br>

## 4. SOLID 관점에서 보는 Factory Method Pattern 🧐

* DIP 준수

  > 추상화 레벨이 높은 클래스와 의존 관계를 맺음으로써 의존성을 낮출 수 있습니다.

<br>

## 5. Factory Method Pattern 활용 🎄🌱

* 어떤 클래스가 자신이 생성해야 하는 객체의 클래스를 예측할 수 없을 때

* 생성할 객체가 많고 동적으로 객체를 생성하고 싶을 때

<br>

### 실제 활용

* java.util 패키지에 있는 Calendar, ResourceBundle, NumberFormat 등의 클래스에서 정의된 getInstance()

* Boolean, Integer, Long 등 Wrapper class 안에 정의된 valueOf()

<br>

## 6. 끝으로...

Q. Factory Method Pattern을 학습하면서 느낀 점은 무엇인가요?

<br>

---

참조 내용 출처

1. https://jdm.kr/blog/180

2. https://readystory.tistory.com/117

3. https://scorpio-mercury.tistory.com/18
