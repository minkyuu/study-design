## 1. "What" is Template Method Pattern? 😮

* 행위 패턴 중 하나로, 소프트웨어 공학에서 동작하는 프로그램의 알고리즘 뼈대를 정의하는 패턴

  > 그리고 이 알고리즘의 뼈대(구조)를 변경하지 않고, 상속받는 하위 클래스에서 알고리즘의 특정 단계들을 다시 정의할 수 있게 해준다.

  > Defines the skeleton of an algorithm in a method, deferring some steps to subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithms structure. – GoF Design Patterns)

<br>

🌱 추가로 토비의 스프링에서는 아래와 같이 정의한다고 합니다.

> 템플릿 메서드 패턴은 상속을 통해 슈퍼클래스의 기능을 확장할 때 사용하는 가장 대표적인 방법. 변하지 않는 기능은 슈퍼클래스에 만들어두고 자주 변경되며 확장할 기능은 서브클래스에서 만들도록 한다. – 토비의 스프링 3.1

<br>


## 2. "Why" we use Template Method Pattern? 🤔

* 코드 중복 최소화

  > 즉, 전체적으로는 동일하면서 부분적으로는 다른 구문으로 구성된 메서드의 코드 중복을 최소화 할 때 유용합니다.

* 자식 클래스의 역할을 감소 + 핵심 로직 관리 용이

  > 동일한 기능을 상위 클래스에서 정의하면서, 확장/변화가 필요한 부분만 서브 클래스에서 구현할 수 있도록 합니다.

* 객체 추가 및 확장을 쉽게 할 수 있습니다.

  > 전체적인 알고리즘은 상위 클래스에서 구현하면서 다른 부분은 하위 클래스에서 구현할 수 있도록 함으로써 전체적인 알고리즘 코드를 재사용하는 데 유용하도록 합니다.

<br><br>

## 3. 잠깐 생각해보기! 🧐

### Q. 스타벅스에 가서 커피를 주문하면 어떤 일이 생길까요??

<br>

<details>
<summary> 스벅 바리스타분들의 음료 제조 프로세스 😎☕</summary>
<div markdown="1">

1. 손님 주문 받기

2. 주문 받은 커피 확인

3. 커피 종류에 따른 레시피 확인 (하위 클래스 구현 사항)

4. 커피 제조 시작             (하위 클래스 구현 사항)

5. 커피 제조 완료 후, 손님에게 커피 제공

</div>
</details>

<br><br>

## 4. "How" to apply Template Method Pattern? ⚒

![Template Method Pattern UML](https://upload.wikimedia.org/wikipedia/commons/2/2a/W3sDesign_Template_Method_Design_Pattern_UML.jpg)

1. 원하는 기능에 대한 구조를 설계하기

2. 필요한 추상 메서드들을 정의하고 설계한 구조에 맞게 Template Method 안에 집어넣기

3. 추상 클래스를 상속 받는 하위 클래스 (Concrete Class)에서 각각의 요구사항에 맞게 메서드 오버라이딩

<br><br>

## 5. SOLID 관점에서 보는 Template Method Pattern

* OCP 준수 (Template Method 수정이 없는 경우!)

  > : 뼈대를 그대로 유지한 채, 상속을 하여 각각 원하는 기능만을 추가할 수 있습니다.

* LSP 준수 

  > : 알고리즘의 뼈대를 그대로 유지한 채, 상속을 하기 때문에 부모 클래스의 역할을 자식 클래스가 항상 대체할 수 있습니다.

<br><br>

## 6. Template Method Pattern 활용

* 코드 중복을 피하고 싶은 경우

* 프레임워크 개발에 많이 활용

<br><br>

## 7. 조금 더 생각해보기!

Q. Template Method Pattern을 쓰다가 전체 구조를 뜯어고쳐야 해서 패턴을 깨야 하는 경우가 생긴 경우에는 어떻게 할까요??

Q. 5번 내용에서 다른 SOLID 원칙들은 어떤가요??

<br><br>


## 8. 끝으로...

Q. Template Method Pattern을 학습하면서 무엇을 느끼셨나요?

<br>

---

참고 내용 출처

1. https://ko.wikipedia.org/wiki/%ED%85%9C%ED%94%8C%EB%A6%BF_%EB%A9%94%EC%86%8C%EB%93%9C_%ED%8C%A8%ED%84%B4

2. https://yaboong.github.io/design-pattern/2018/09/27/template-method-pattern/

3. https://gmlwjd9405.github.io/2018/07/13/template-method-pattern.html

4. https://niceman.tistory.com/142

