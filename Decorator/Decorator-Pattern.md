## 1. "What" is Decorator Pattern ? ๐
>: ๊ตฌ์กฐ ํจํด ์ค ํ๋๋ก, **"๊ธฐ๋ณธ ๊ฐ์ฒด๋ ์ ์งํ๋"** ํ์ํ  ๋๋ง๋ค **"์ถ๊ฐ์ ์ธ ๊ธฐ๋ฅ์ ๋์ ์ผ๋ก ์ ์ฐํ๊ฒ ํ์ฅ"** ํ  ์ ์๊ฒ ํด์ฃผ๋ ํจํด

<br>

## 2. "Why" Decorator Pattern? ๐ค

Decorator Pattern์ ์ฅ์ 

* ๊ธฐ์กด์ ๊ฐ์ฒด์ ์ฝ๋๋ฅผ ์์ ํ์ง ์๊ณ  ๊ธฐ๋ฅ์ **"๋์ ์ผ๋ก"** ํ์ฅํ  ์ ์๋ค.

<br>

## Q. ์ค๋๊ฐ๋ง์ Subway์ Sandwich๋ฅผ ๋จน๋ฐฉํ๋ฌ์จ ๋ผ์ด์ธ ๐
<details>
<summary> Q. ๊ทธ๋ฐ๋ฐ Subway์์ ์๋์์น๋ฅผ ์ฃผ๋ฌธํ๋ ค๋ฉด?๐ฅช </summary>
<div markdown="1">
 
<br>

![๋ฉ๋ด์ ํ](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdqnbPP%2FbtqRGpVlsPM%2Fa6UUO86DIhYYkvxYkGWbf1%2Fimg.png)

![๋นต์ ํ](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc3zRrN%2FbtqRI8MzWVL%2FvgsEYWw7r9jgR1tJ8aY5DK%2Fimg.png)

![์ถ๊ฐํ ํ์ ํ](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fp5tQK%2FbtqRrPIbazU%2FKyC9Kwscreym8VN6RGizsK%2Fimg.png)

![์ผ์ฑ์์ค์ ํ](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbeloAF%2FbtqRAjuzT9r%2F6zra9XQkOLLV3h5MftAzZK%2Fimg.png)

>: ํ๋ก์ธ์ค๋ฅผ ๋ณด๋ฉด ๊ณ์ํด์ ๋์ ์ผ๋ก ๋ฌด์ธ๊ฐ๋ฅผ ์ถ๊ฐํด์ผ ํ๋ค.

</div>
</details>

<br>

## 3. "How" to apply Decorator Pattern?

### 3.1. Decorator Pattern UML Diagram ๐จ๐

![Decorator UML](https://blog.kakaocdn.net/dn/17xZn/btrd9k6XuUx/rplqedHD5wKFnsB1phyhDK/img.gif)

<details>
<summary> ๊ฐ ์์ ์ค๋ช </summary>
<div markdown="1">

<br>  

- Component (Interface)

>: ๋์ ์ผ๋ก ์ถ๊ฐํ  ์๋น์ค๋ฅผ ๊ฐ์ง ์ ์๋ ๊ฐ์ฒด

- ConcreteComponent

>: ์ถ๊ฐ์ ์ธ ์๋น์ค๊ฐ "ํ์ํ" ์ค์  ๊ฐ์ฒด

- Decorator

>: Component์ ์ฐฝ์กฐ์๋ฅผ ๊ด๋ฆฌํ๋ฉด์ Component์ ์ ์๋ ์ธํฐํ์ด์ค๋ฅผ ๋ง์กฑํ๋๋ก ์ ์

- ConcreteDecorator

>: ์๋กญ๊ฒ ์ถ๊ฐ๋๋ ์๋น์ค๋ฅผ ์ค์  ๊ตฌํํ ํด๋์ค๋ก addBehavior()๋ฅผ ๊ตฌํํ๋ค.
</div>
</details>

<br>

### 3.2. Decorator Pattern ๊ตฌํํ๊ธฐ!

<details>
<summary> ๊ตฌํ Process </summary>
<div markdown="1">

<br>  

1. Component(interface), ConcreteComponent ์ ์
  
2. Component๋ฅผ ๊ตฌํํ Decorator๋ฅผ Component์ ์งํฉ ๊ด๊ณ ์์ฑ

```
์งํฉ(Aggregation) ๊ด๊ณ
  
  : ํ ๊ฐ์ฒด๊ฐ ๋ค๋ฅธ ๊ฐ์ฒด๋ฅผ ํฌํจํ๋ ๊ฒ (๋ถ๋ถ์ ๋ํ๋ด๋ ๊ฐ์ฒด๋ฅผ ๋ค๋ฅธ ๊ฐ์ฒด์ ๊ณต์ ํ  ์ ์๋ค)

  : Diagram์์ "์ ์ฒด"๋ฅผ ๊ฐ๋ฆฌํค๋ ํด๋์ค ๋ฐฉํฅ์ ๋น ๋ง๋ฆ๋ชจ๋ก ํ์
  (์์กดํ๋ ๊ฐ์ฒด = ์ ์ฒด , ์์กด๋ฐ๋ ๊ฐ์ฒด = ๋ถ๋ถ)
  
  : ์์ฑ์์์ ์ฐธ์กฐ๊ฐ์ ์ธ์๋ก ๋ฐ์ ํ๋ ์ด๊ธฐํ
  
  (Composition ๊ด๊ณ๋ ์๋๋ฐ ๋์ค์ ๊ณต๋ถํด๋ณด๋ฉด ์ข์ ๊ฒ ๊ฐ์ต๋๋ค!)
```
  
3. ํ์๋ก ํ๋ ์๊ตฌ์ฌํญ์ ๋ง๊ฒ ๊ฐ๊ฐ์ ๊ธฐ๋ฅ๋ค์ ํ์ฅ!!

</div>
</details>


<br>

## 4. SOLID ๊ด์ ์์ ๋ณธ Decorator Pattern ๐ง

* OCP ์ค์

>: ๊ธฐ์กด ์ฝ๋์ ์์ ์ ํ์ง ์๊ณ , ํ์ํ ๊ธฐ๋ฅ์ ์์ ๋กญ๊ฒ ํ์ฅํ  ์ ์์ต๋๋ค.

* DIP ์ค์

>: Component๊ฐ ConcreteDecorator์ ์ง์  ๊ด๊ณ๋ฅผ ๋งบ๋ ๊ฒ์ด ์๋ Decorator์ ์์กด ๊ด๊ณ๋ฅผ ๋งบ๊ณ  ์์ต๋๋ค.

<br>


## 5. ๋์ผ๋ก

Q. Decorator Pattern์ ์ดํด๋ณด๋ฉด์ ๋ฌด์์ ๋๋ผ์จ๋์??

<br>

---

๋ด์ฉ ์ถ์ฒ

1. https://victorydntmd.tistory.com/297

2. ์งํฉ ๊ด๊ณ1 (https://velog.io/@ha0kim/IoCDI-%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85)

3. ์งํฉ ๊ด๊ณ2 (https://gmlwjd9405.github.io/2018/07/04/class-diagram.html)

4. DP ํ์ฉ (https://mnworld.co.kr/1739)
