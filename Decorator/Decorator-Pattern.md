## 1. "What" is Decorator Pattern ? 🎄
>: 구조 패턴 중 하나로, **"기본 객체는 유지하되"** 필요할 때마다 **"추가적인 기능을 동적으로 유연하게 확장"** 할 수 있게 해주는 패턴

<br>

## 2. "Why" Decorator Pattern? 🤔

Decorator Pattern의 장점

* 기존의 객체의 코드를 수정하지 않고 기능을 **"동적으로"** 확장할 수 있다.

<br>

## Q. 오래간만에 Subway에 Sandwich를 먹방하러온 라이언 🙄
<details>
<summary> Q. 그런데 Subway에서 샌드위치를 주문하려면?🥪 </summary>
<div markdown="1">
 
<br>

![메뉴선택](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdqnbPP%2FbtqRGpVlsPM%2Fa6UUO86DIhYYkvxYkGWbf1%2Fimg.png)

![빵선택](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc3zRrN%2FbtqRI8MzWVL%2FvgsEYWw7r9jgR1tJ8aY5DK%2Fimg.png)

![추가토핑선택](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fp5tQK%2FbtqRrPIbazU%2FKyC9Kwscreym8VN6RGizsK%2Fimg.png)

![야채소스선택](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbeloAF%2FbtqRAjuzT9r%2F6zra9XQkOLLV3h5MftAzZK%2Fimg.png)

>: 프로세스를 보면 계속해서 동적으로 무언가를 추가해야 한다.

</div>
</details>

<br>

## 3. "How" to apply Decorator Pattern?

### 3.1. Decorator Pattern UML Diagram 🎨🖌

![Decorator UML](https://blog.kakaocdn.net/dn/17xZn/btrd9k6XuUx/rplqedHD5wKFnsB1phyhDK/img.gif)

<details>
<summary> 각 요소 설명 </summary>
<div markdown="1">

<br>  

- Component (Interface)

>: 동적으로 추가할 서비스를 가질 수 있는 객체

- ConcreteComponent

>: 추가적인 서비스가 "필요한" 실제 객체

- Decorator

>: Component의 창조자를 관리하면서 Component에 정의된 인터페이스를 만족하도록 정의

- ConcreteDecorator

>: 새롭게 추가되는 서비스를 실제 구현한 클래스로 addBehavior()를 구현한다.
</div>
</details>

<br>

### 3.2. Decorator Pattern 구현하기!

<details>
<summary> 구현 Process </summary>
<div markdown="1">

<br>  

1. Component(interface), ConcreteComponent 정의
  
2. Component를 구현한 Decorator를 Component와 집합 관계 생성

```
집합(Aggregation) 관계
  
  : 한 객체가 다른 객체를 포함하는 것 (부분을 나타내는 객체를 다른 객체와 공유할 수 있다)

  : Diagram에서 "전체"를 가리키는 클래스 방향에 빈 마름모로 표시
  (의존하는 객체 = 전체 , 의존받는 객체 = 부분)
  
  : 생성자에서 참조값을 인자로 받아 필드 초기화
  
  (Composition 관계도 있는데 나중에 공부해보면 좋을 것 같습니다!)
```
  
3. 필요로 하는 요구사항에 맞게 각각의 기능들을 확장!!

</div>
</details>


<br>

## 4. SOLID 관점에서 본 Decorator Pattern 🧐

* OCP 준수

>: 기존 코드의 수정을 하지 않고, 필요한 기능을 자유롭게 확장할 수 있습니다.

* DIP 준수

>: Component가 ConcreteDecorator와 직접 관계를 맺는 것이 아닌 Decorator와 의존 관계를 맺고 있습니다.

<br>


## 5. 끝으로

Q. Decorator Pattern을 살펴보면서 무엇을 느끼셨나요??

<br>

---

내용 출처

1. https://victorydntmd.tistory.com/297

2. 집합 관계1 (https://velog.io/@ha0kim/IoCDI-%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85)

3. 집합 관계2 (https://gmlwjd9405.github.io/2018/07/04/class-diagram.html)

4. DP 활용 (https://mnworld.co.kr/1739)
