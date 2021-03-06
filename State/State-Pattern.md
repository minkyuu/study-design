## 1. "What" is State Pattern? ๐ฎ
* ๊ฐ์ฒด ์์ ์ **"๋ด๋ถ ์ํ์ ๋ฐ๋ผ"** ๊ฐ์ฒด์ ํ์๋ฅผ ๋ณ๊ฒฝํ  ์ ์๋๋ก ํ๋ ํจํด

<br>

## 2. "Why" we use State Pattern? ๐ค

### State Pattern์ ์ฌ์ฉํ์ง ์์ ๊ฒฝ์ฐ

* if ~ else , switch ์กฐ๊ฑด๋ฌธ์ ์ฌ์ฉํ๊ฒ ๋๋๋ฐ, ์ด๋ฐ ๊ตฌ์กฐ๋ ์ํ ํ์ด๋ธ์ ๋ณํ์ํค๊ฑฐ๋ ์๋ก์ด ์ํ๋ฅผ ์ถ๊ฐํ๋ ๊ฒ์ด ์ฝ์ง ์์ต๋๋ค.
  
    > (์๋ก์ด ์ํ๋ฅผ ์ถ๊ฐํ  ๋, ๋ง์ ๋ฉ์๋๋ฅผ ๋ณ๊ฒฝํด์ฃผ์ด์ผ ํฉ๋๋ค.)

<br>

### State Pattern์ ์ฅ์ 

1. ์๋ก์ด ์ํ๊ฐ ์ถ๊ฐ๋๋๋ผ๋ Context ์ฝ๋๊ฐ ๋ฐ๋ ์ํฅ์ ์ต์ํ

2. ํด๋์ค๋ฅผ ์ถ๊ฐํ๋๋ผ๋ ๊ธฐ์กด์ ๋ฉ์๋์ ์ฝ๋๋ ๊ทธ๋๋ก ์ ์ง

3. ํ ์ํ์ ๋ฐ๋ฅธ ๋์์ ๊ตฌํํ ์ฝ๋๊ฐ ์ํ๋ณ๋ก ๊ตฌ๋ถ๋๊ธฐ ๋๋ฌธ์ ์ํ๋ณ ๋์์ ์์ ํ๊ธฐ ์ฝ๋ค

<br>

## 3. "How" to apply State Pattern? ๐ง

![State Pattern UML](https://media.vlpt.us/images/y_dragonrise/post/b0cd2535-b0f8-4aa6-8fdc-7c1c164e89b2/image.png)

1. State ์ค๊ณ
    * Concrete State ์ ์
    
    * State (interface)๋ก Concrete State๋ค์ ์บก์ํํ๊ธฐ

2. Context์ State (interface) ์ฌ์ด์ ์์กด ๊ด๊ณ ์์ฑ
    
    * Context์ State๋ฅผ ์์กด ์ฃผ์ํ๋ ๋ฐฉ์์ผ๋ก ๊ด๊ณ๋ฅผ ์์ฑ (์๋์ 3๊ณผ ์ฐ๊ฒฐ๋ฉ๋๋ค)
    
3. Context์์ ๋์ ์ผ๋ก ์ํ๊ฐ ๋ณํ์ํฌ ์ ์๋๋ก setter ๋ฉ์๋ ์์ฑ, state ํธ์ถ ๋ฉ์๋ ์์ฑ

<br>


## 4. State Pattern ํ์ฉ ๐ 

* ๊ฐ์ฒด์ ํ๋์ด ์ํ์ ๋ฐ๋ผ ๋ณํ๊ฐ ํ์ํ ๊ฒฝ์ฐ ํ์ฉ

  > ์ฆ, ๊ฐ์ฒด์ ์ํ์ ๋ฐ๋ผ ๋ฐํ์์ ํ๋์ด ๋ฐ๋์ด์ผ ํ๋ ๊ฒฝ์ฐ


<br>

## 5. SOLID ๊ด์ ์์ ๋ณธ State Pattern

* OCP ์ค์

>: ์๋ก์ด ์ํ ์ถ๊ฐ ์, ๊ธฐ์กด์ ์ฝ๋์ ์ํฅ์ ์ฃผ์ง ์์ต๋๋ค.

* DIP ์ค์

>: Concrete State ํด๋์ค๊ฐ ์๋ ์ธํฐํ์ด์ค State์ ์์กด ๊ด๊ณ๋ฅผ ๊ฐ์ต๋๋ค.

<br>


## 6. ์๊ฐํด๋ณด๊ธฐ! ๐ค

Q. State Pattern vs Strategy Pattern , ๋ ํจํด์ ์ด๋ป๊ฒ ๋ค๋ฅธ ๊ฒ์ผ๊น์??

[์ฐธ๊ณ  ๋ด์ฉ](https://github.com/KWSStudy/Refactoring/issues/2) 

<br>

<details>
<summary>๋ ํจํด์ UML ๋น๊ต</summary>
<div markdown="1">
  
<br>
  
### Strategy Pattern UML

![Strategy Pattern](https://media.vlpt.us/images/y_dragonrise/post/01b02920-5e7d-4a90-b5be-7cdfe0f6091d/image.png)

<br>
  
### State Pattern UML

![State Pattern UML](https://media.vlpt.us/images/y_dragonrise/post/b0cd2535-b0f8-4aa6-8fdc-7c1c164e89b2/image.png)


### ์ถ๊ฐ ๋ด์ฉ
  
State Pattern
  
  > ์ํ ํจํด์ ์ํ์ ๋ฐ๋ผ์ ํ๋์ด ๋ฐ๋ผ๊ฐ๋ค. (์๋์ ์ธ ๋๋)
  
Strategy Pattern
  
  > ์ ๋ต ํจํด์ ์ด๋ค ์ํ๋ ๋ชฉํ๋ฅผ ์ด๋ฃจ๊ธฐ ์ํด์ ํ๋์ ์ทจํ๋ค. (๋ฅ๋์ ์ด๊ณ , ๋ฏธ๋์งํฅ์ )
  
</div>
</details>

  
<br>

## 7. State Pattern์ ๋ง์น๋ฉด์ 

Q. State Pattern์ ํ์ตํ์๋ฉด์ ์ด๋ค ๊ฒ์ ๋๋ผ์จ๋์?

<br>

---
์ฐธ์กฐ ๋ด์ฉ ์ถ์ฒ

1. https://victorydntmd.tistory.com/294

2. https://kscory.com/dev/design-pattern/state

3. https://always-intern.tistory.com/9

4. https://tecoble.techcourse.co.kr/post/2021-04-26-state-pattern/
