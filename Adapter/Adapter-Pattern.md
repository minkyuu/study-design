## 1. "What" is Adapter Pattern?

>: 호환되지 않는 기존 클래스의 인터페이스를 변환하여 사용할 수 있도록 만드는 패턴




<br>

### Q. 이게 도대체 무슨 말이지??

어댑터를 한 번 떠올려봅시다! 라이언은 일본으로 여행을 가게 되었습니다. 

여행을 잘하고 숙소에 도착하여 스마트폰을 충전하려고 하는데 플러그 모양이 우리나라에서 사용하는 것과 다르게 1자 모양으로 두 개가 있어서 충전을 못하는 상황이 발생하였습니다...

<br>

### Q. 이 때 라이언은 스마트폰을 충전하기 위해서 어떻게 해야 할까요??

1. 충전기를 새로 산다

>: 이 경우에는 가져온 노트북 충전기도 새로 사야 한다 (난 돈 쓰는게 너무 좋고 충전기 수집하는게 좋다면 나쁘지 않습니다^^;)

2. 어댑터만 새로 사서 사용한다

>: 어댑터 하나만 샀을뿐인데 스마트폰, 노트북을 자유롭게 충전을 할 수 있다

<br>

<details>
<summary>Adapter(돼지코) 사진🐷</summary>
<div markdown="1">

### 110V 어댑터🐷

![110V 어댑터](https://m.intelrior.com/web/product/big/201812/d0f759fcb1ce4fca73caeff0b1b63036.jpg)

### 220V 어댑터🐷

![220V 어댑터](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT6BDcj-g7Szu9V3fZzTWSBn2zM0pzy5yBBmA&usqp=CAU)

</div>
</details>

<br>

## 2. "Why" Adapter Pattern?

Adapter Pattern의 장점

1. 기존 코드를 변경하지 않아도 된다.

2. 클래스의 재사용성을 높일 수 있다.

<br>

## 3. "How" Adapter Pattern?

<details>
<summary>🐷Answer (한 번 생각해보고 열어보세요!)</summary>
<div markdown="1">

<br>

![Adapter Pattern Structure](https://t1.daumcdn.net/cfile/tistory/24231F4C575EACA210)

> Adapter Pattern 구조 (이미지 출처 : https://jusungpark.tistory.com/22)

<br>

라이언(Client)이 스마트폰(Adaptee)를 충전하기 위해서

1. 호환성이 맞지 않아 변경하고자 하는 부분(Target)을 생성합니다. 

2. 이를 변경할 수 있도록 해주는 Target을 implements한 어댑터(Adapter)를 생성합니다.

    < Key Point >
    
    * 변경하려는 Target(110V) implements로 구현한다.
    
    * 변경하기 전 Target(220V) 필드로 가지고 있고 
    
    * 변경하기 전 Target(220V) 메서드를 Override 한 메서드 (110V) 안에서 호출한다.

</div>
</details>

<br>

## 4. SOLID 관점에서 보는 Adapter Pattern

* 기존의 코드의 수정은 없이 그대로 사용한 점에서 OCP를 준수하였다고 볼 수 있습니다.

<br>

## 5. Adapter Pattern의 활용
* 기존의 코드에 새로운 코드를 연동하여 사용하고 싶은데, 두 코드의 인터페이스가 달라 사용할 수 없는 경우

<br>

## 6. 끝으로... (About Design Pattern)
* Adapter Pattern을 학습하면서 무엇을 느끼셨나요?

* 외우려고 하기 보다 Pattern을 음미하셨으면 좋겠습니다. 그래서 여러 방식으로 활용을 할 수 있게 되면 좋을 것 같습니다.

<br>

---

참조 블로그 링크

1. https://jusungpark.tistory.com/22
2. https://kscory.com/dev/design-pattern/adapter
3. https://dailyheumsi.tistory.com/189
