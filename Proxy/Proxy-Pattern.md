## 1. "What" is the Proxy Pattern?


* 구조 패턴 중 하나로, 어떤 객체에 대한 접근을 제어하는 용도로 실제 기능을 수행하는 객체(Real Object) 대신
  가상의 객체(Proxy Object)를 사용해 로직의 흐름을 제어하는 디자인 패턴입니다.

  > 흐름제어만 할 뿐 결과값을 조작하거나 변경시키면 안됩니다.

  > Proxy 는 대리, 대리인이라는 뜻을 가진 단어

<br>

## 2. "Why" do we use Proxy Pattern?

* 핵심 객체의 복잡성을 클라이언트에게 노출하지 않기 위해서 wrapper를 생성하고자 할 때 사용한다.

  > (원문 : Proxy pattern is used when we need to create a wrapper to cover the main object’s complexity from the client.)

<br>

Proxy Pattern의 장점

* 기본 객체의 리소스가 무거운 경우, 프록시 객체에서 간단한 처리를 하거나 기본 객체를 캐싱 처리함으로써 부하를 줄일 수 있다.

* 기본 객체에 대한 수정 없이, 클라이언트에서의 사용과 기본 객체 사이에 일련의 로직을 프록시 객체를 통해 넣을 수 있다.

* 프록시는 기본 객체와 요청 사이에 있기 때문에, 일종의 방패(보안)의 역할도 한다.

* 구조나 코드 구현이 간단함.

<br>

Proxy Pattern의 단점

* 프록시 객체가 중간에 껴있기 때문에, 간혹 응답이 느려질 수 있다. (캐싱이 안되어있는 초기 사용의 경우)

<br>

## 3. "How" to apply Proxy Pattern?

### 3.1. Proxy Pattern Class Diagram

![Proxy Pattern Class Diagram](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F99A46433599FE0A41E)

<br>

<details>
<summary>각 요소 설명</summary>
<div markdown="1">

<br>

Subject

* Proxy 와 RealSubject 가 구현해야하는 인터페이스

* 두 객체를 동일하게 다루기 위해 존재

Proxy

* RealSubect 와 Client 요청 사이에 존재하는 객체

* Subject 를 구현함으로써 클라이언트는 RealSubject 사용하는 것과 별 차이가 없어야 한다.

RealSubject

* 실질적으로 요청에 대해 주된 기능을 수행하는 객체

* Proxy 객체는 내부적으로 이 객체를 로직에 맞게 사용한다. (위임)

</div>
</details>

<br>

### 3.2. 구현 프로세스

1. 원래 구조 분석

2. 주요 기능을 하는 객체의 상위에 인터페이스를 정의하여 프록시 객체와 연결합니다.

3. 프록시 객체에서는 흐름 제어만 해줄 수 있도록 정의합니다. 

    > 주요 기능을 하는 객체를 건드리지 않는 선에서 부수적인 기능 추가는 가능!

4. 클라이언트에서 프록시 객체를 통해 접근합니다.

<br>

## 4. SOLID 관점에서 보는 Proxy Pattern

* SRP 준수

  > 실제 객체와 프록시 객체의 책임이 분리되어있다.

* OCP 준수

  > 프록시 객체를 사용하는 객체 관점에서는 새로운 기능이 추가되어도 여전히 프록시 객체인지 진짜 객체인지 알 수가 없다.

* DIP 준수

  > 클라이언트에서 프록시 객체와 프록시 객체를 사용하는 객체에 접근할 때 모두 추상화된 인터페이스를 통해 접근할 수 있다.


<br>

## 5. Proxy Pattern의 활용

1. 주로 프록시 패턴은 RealSubject 가

    * 원격 시스템에서 돌아가거나,

    * 그 객체의 생성 비용이 많이 들어 실제 사용 시점에 객체를 생성하거나,

    * 실제 객체에 접근을 제한 및 제어를 해야 할 때 등 의 경우에 사용 됩니다.

2. 원래 하려던 기능을 수행하며 그외의 부가적인 작업(로깅, 인증, 네트워크 통신 등)을 수행하기에 좋습니다.

3. 비용이 많이 드는 연산(DB 쿼리, 대용량 텍스트 파일 등)을 실제로 필요한 시점에 수행할 수 있습니다.

<br>

### 정리

* 기본 객체가 리소스 집약적인 경우. 자잘한 작업들은 프록시 객체가 처리하게 한다.

* 기본 객체에 접근을 제어해야하는 경우. 프록시 객체가 권한에 따라 접근 로직을 다르게 처리하게 한다


<br>

## 6. Proxy Pattern의 종류

- 원격 프록시 (Remote Proxy)

- 가상 프록시 (Virtual Proxy)

- 보호 프록시 (Protection Proxy)

- 방화벽 프록시 (Firewall Proxy)

- 스마트 레퍼런스 프록시 (Smart Reference Proxy)

- 캐싱 프록시 (Caching Proxy)

- 동기화 프록시 (Synchronization Proxy)

- 복잡도 숨김 프록시 (Complexity Hiding Proxy)

- 지연 복사 프록시 (Copy-On-Write Proxy)

<br>

<details>
<summary>상세 설명</summary>
<div markdown="1">

- 원격 프록시 (Remote Proxy)

  >: 원격 객체에 대한 접근 제어가 가능합니다.

- 가상 프록시 (Virtual Proxy)

  >: 객체의 생성비용이 많이 들어 미리 생성하기 힘든 객체에 대한 접근 및 생성시점 등을 제어합니다.

- 보호 프록시 (Protection Proxy)

  >: 객체에 따른 접근 권한을 제어해야하는 객체에 대한 접근을 제어할 수 있습니다.

- 방화벽 프록시 (Firewall Proxy)

  >: 일련의 네트워크 자원에 대한 접근을 제어함으로써 주 객체를 '나쁜' 클라이언트들로부터 보호하는 역할을 합니다.

- 스마트 레퍼런스 프록시 (Smart Reference Proxy)

  >: 주 객체가 참조될 때마다 추가 행동을 제공합니다. ex) 객체 참조에 대한 선 작업, 후 작업 등

- 캐싱 프록시 (Caching Proxy)

  >: 비용이 많이 드는 작업의 결과를 임시로 저장 하고, 추후 여러 클라이언트에 저장된 결과를 실제 작업처리 대신 보여주고 자원을 절약하는 역할을 합니다.

- 동기화 프록시 (Synchronization Proxy)

  >: 여러 스레드에서 주 객체에 접근하는 경우에 안전하게 작업을 처리할 수 있게 해줍니다. 주로 분산 환경에서 일련의 객체에 대한 동기화 된 접근을 제어해주는 자바 스페이스에서 쓰입니다.

- 복잡도 숨김 프록시 (Complexity Hiding Proxy)

  >: 복잡한 클래스들의 집합에 대한 접근을 제어하고, 복잡도를 숨깁니다.

- 지연 복사 프록시 (Copy-On-Write Proxy)

  >: 클라이언트에서 필요로 할 때까지 객체가 복사되는 것을 지연시킴으로써 객체의 복사를 제어합니다. '변형된 가상 프록시'라고 할 수 있으며,

  >: Java 5 의 CopyOnWriteArrayList 에서 쓰입니다.

</div>
</details>


<br>


## 7. 생각해보기

Q. Spring을 공부하다 보면 나오는 "AOP"에서의 Proxy는 과연 어떨까요?

[AOP 관련 내용](https://sa1341.github.io/2019/05/25/%EC%8A%A4%ED%94%84%EB%A7%81-AOP-%EA%B0%9C%EB%85%90-%EB%B0%8F-Proxy%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EA%B5%AC%EB%8F%99%EC%9B%90%EB%A6%AC/)


<br>

---

참고 내용 출처

1. https://limkydev.tistory.com/79

2. https://www.geeksforgeeks.org/proxy-design-pattern/

3. https://developside.tistory.com/80

4. https://dailyheumsi.tistory.com/201

5. https://velog.io/@ljinsk3/%EB%94%94%EC%9E%90%EC%9D%B8-%ED%8C%A8%ED%84%B4-Proxy-Pattern


--- 

활용 관련 참고 블로그

1. 웹 캐시 (https://fsd-jinss.tistory.com/35)

2. 데이터베이스 캐시 (https://tmdahr1245.tistory.com/120)

3. https://www.kdata.or.kr/info/info_04_view.html?field=&keyword=&type=techreport&page=252&dbnum=127324&mode=detail&type=techreport
