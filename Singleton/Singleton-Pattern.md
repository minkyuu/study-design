## 1. "What" is Singleton Pattern
>: 인스턴스가 프로그램 내에서 오직 하나만 생성되는 것을 보장하고, 프로그램 어디에서든 이 인스턴스에 접근할 수 있도록 하는 패턴

> ex. 프린터, 음료 자판기

<br>

## 2. "Why" Singleton Pattern??
Singleton Pattern의 장점

1. 생성되는 인스턴스가 딱 한 개이므로, 메모리 공간을 절약할 수 있습니다.

2. 여러 번 자주 호출하게 되는 객체였다면, 매 번 생성하는 시간이 없어지므로 객체 로딩 시간이 줄어들게 됩니다. 

3. 싱글톤 패턴으로 생성된 인스턴스는 전역 변수처럼 사용된다. (다른 인스턴스들과 데이터 공유가 잘 이루어집니다.)


<br>

## 3. "How" 인스턴스를 "딱 하나"만을 생성하려면 어떻게 해야 할까요???

<details>
<summary>Answer (잠시 생각을 해본 후 열어보세요!)</summary>
<div markdown="1">

```java
1. private 선언을 한 인스턴스, 생성자
2. instance 에 접근할 수 있는 메서드

class Singleton {
    private static Singleton instance = null;
    
    private Singleton() {}
    
    public static Singleton getInstance(){
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
    
// 처음 싱글톤 객체 생성되는 부분도 문제 없도록 개선
class Singleton {
    private static Singleton instance = new Singleton();
    
    private Singleton() {}
    
    public static Singleton getInstance() {
        return instances;
    }
}
```
</div>
</details>

<br>

## 4. SOLID로 살펴본 Singleton Pattern과 Singleton Pattern의 문제점
1. 클래스 내부에서 객체를 직접 생성하기 때문에 DIP를 위배하게 됩니다.
2. 생성된 인스턴스가 다른 클래스의 인스턴스들과 많은 데이터를 공유할 경우 OCP를 위배하게 됩니다.
3. 많은 데이터들을 공유할 수 있는 부분때문에 멀티스레드 환경에서 스레드를 안전하게 구현하려면(Thread-safe) 동기화 처리를 해줘야 한다.

<br>

## 5. 자판기의 예시를 통해서 보는 Singleton Pattern.

Q. 음료 자판기에 콜라가 딱 한 개가 남아있습니다. 두 명의 사람이 동시에 음료를 뽑는 버튼을 누르면 어떻게 될까요?

>: 당연하게도 콜라를 마실 줄 알았던 사람 중 한 명은 콜라를 마시지 못하는 상황이 벌어지게 됩니다.

<br>

이 상황을 프로그래밍 개념에서 보면 어떨까요?

- 여러 사용자 or 쓰레드에서 싱글톤 객체에 동시 접근하는 것이라고 생각할 수 있습니다.

- 이를 해결하기 위해서 synchronized (동기화) 개념이 필요합니다.

>: 동기화는 간단하게 말해 해당 Thread 외 동시 접근을 못하게 하도록 막는 것이라고 생각하면 됩니다.

<br>
<br>

<details>
<summary> 동기화 관련 내용 </summary>
<div markdown="2">

<br>

바로 코드를 통해 살펴보겠습니다.

```java
public class Singleton {
    private static Singleton instance = null;
    
    private Singleton() {}
    
    public synchronized static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

* synchronized 키워드를 통해서 thread-safe하게 만든 코드입니다.
* 이를 통해서 각 Thread의 접근이 동시적으로 이루어지지 않도록 해두었습니다.

### But! synchronized 특성상 성능저하가 발생하므로 권장하지 않는 방법입니다.

<br>

## 성능 개선 방법
방법 1. Thread safe lazy initialization + Double-checked locking

>: 지연 초기화를 통한 성능 개선

```java
public class ThreadSafeLazyInitialization {
 
    private volatile static ThreadSafeLazyInitialization instance;
 
    private ThreadSafeLazyInitialization(){}
     
    public static ThreadSafeLazyInitialization getInstance(){
        if(instance == null){
            synchronized (ThreadSafeLazyInitialization.class) {
                if(instance == null)
                    instance = new ThreadSafeLazyInitialization();
            }
 
        }
        return instance;
    }
}
```

<br>

방법 2. Initialization on demand holder idiom (holder에 의한 초기화)

>: 클래스(Singleton Object) 안에 클래스(Holder)를 두어 JVM의 class loader 매커니즘과 Class가 로드되는 시점을 이용한 방법

>: 가장 많이 사용되는 LazyHolder를 사용하는 Singleton Pattern

```java
public class Something {
    private Something() {
    }
 
    private static class LazyHolder {
        public static final Something INSTANCE = new Something();
    }
 
    public static Something getInstance() {
        return LazyHolder.INSTANCE;
    }
}
```

내용 출처 : https://injae-kim.github.io/dev/2020/08/06/singleton-pattern-usage.html

</div>
</details>
<br>


## 6. Singleton Pattern 활용

1. 하드웨어 기기의 인터페이스 (ex. 프린터)
2. 로거 (= 로그 파일 생성 클래스)
3. 환경설정 파일
4. 캐시

5+@ : 찾아보면 사용하는 케이스들이 더 많이 있을 것 같습니다.

<br>

## 결론
* Singleton Pattern이 어떤 것이고(What) 어떤 특징을 가지고 있는지 아는 것!
* 그리고 상황에 따라 적절하게 사용할 수 있기 위해 어떻게(How) 구현하지 아는 것!
* 추가로 메모리 개념에서 Singleton Pattern을 접근해보는 것!

---

출처 1 : https://jeong-pro.tistory.com/86

출처 2 : https://velog.io/@kyle/%EC%9E%90%EB%B0%94-%EC%8B%B1%EA%B8%80%ED%86%A4-%ED%8C%A8%ED%84%B4-Singleton-Pattern

동기화 내용 출처 : https://link2me.tistory.com/1732
