# 2.5 연산자 우선순위, 소수 계산 주의점

* 코드를 짤 때도 연산자의 우선순위가 있다 마치 사칙연산처럼
* 연산자의 우선순위를 다 외우는것은 사실상 힘듬 ()가 가장 우선순위 1번임
* 계산에 관련된 우선순위는 사칙연산과 동일
<br/>
<br/>

컴퓨터가 정확하다는 편견은 갖지 말아야한다. 
```js
> 0.1 + 0.2
< 0.30000000000000004
```
이렇게 결과 값이 나온다 즉, 컴퓨터는 소수계산을 잘 못한다 이유는 컴퓨터는 이진법으로 되어있기 때문

이러한 문제를 해결하기 위한 방법이 무엇이 있을까???

```js
> (0.1 * 10 + 0.2 * 10) / 10
< 0.3
```
이런식으로 10을 곱해서 정수로 만들어 준뒤 다시 10을 나누면 된다.
<br/>
<br/>

---
# 2.6 불 값, (boolean, 값들의 비교)

## 불 값 (boolean)

컴퓨터는 1 과 0 밖에 모른다. 1은 참(true), 0은 거짓(false)에 대응된다 <br/>자바스크립에도 true와 false를 나타내는 boolean이라는 자료형이 있다.

```js
> typeof(true);
< boolean
```
```js
> typeof('true');
< String
```
위에 두개의 자바스크립트를 비교해보면 'true'와 true는 다르다는것을 알 수 있다.
 
불 값은 주로 참, 거짓을 판별할 때 사용이 된다.

```js
> 5 > 2;
< true

> 5 < 2;
< false
```

* 특이사항

자바스크립트는 참 거짓을 비교할 때 특이사항들이 많다.

```js
> true > false;
< true
// true = 1, false = 0 이라서 성립.

> 'a' > 'b';
< false
// b가 a보다 문자 번호가 크다.(b는 98, a는 97)

> 'ad' > 'ab';
< true
// 문자의 비교는 사전 순 이라고 생각하면 편함 (d가 b보다 뒤에 나오니 더 크다.)

> '3' > 4;
< false
// 숫자 vs 문자열형태의 숫자 비교 시 문자열이 숫자로 바뀜

> 'abc' > 4;
< false
// 'abc'는 NaN 으로 바뀌면서 NaN 과 4의 비교, NaN은 무엇과 비교해도 false
```

<참고> 문자의 번호 알아보기

문자의 번호를 알아보려면 charCodeAt을 이용함. 찾고자 하는 문자열 뒤에 .charCodeAt()을 붙이면 문자의 번호가 나옴.

```js
> 'a'.charCodeAt();
< 97
```

* ==와 === 차이 이해하기
```js
> '1' == 1;
< true

> 1 == true;
< true

> 1 == '1';
< true

> '1' === 1;
< false

> 1 === true;
< false

> 1 === '1';
< false
```

위를 보면 ==는 값만 비교하고 자료형은 비교하지 않는다.

하지만 ===는 값과 자료형 둘다 비교를 한다.
<br/>
<br/>

---
# 2.7 논리연산자

불 값은 논리식을 다룰 때 많이 표현된다. 시험 문제 중 "다음 문장이 참인지 거짓인지 고르시오"라는 문제를 본 적이 있을 거다. 이때 참과 거짓이 바로 불 값의 참, 거짓과 대응된다.

"10은 8보다 크다. 그리고 5는 8보다 작다"라는 문장은 참일까, 거짓일까? 그리고 이 문장을 자바스크립트로 어떻게 표현할 수 있을까?

```js
> 10 > 8 && 5 < 8 ; // 여기서 &&는 and(그리고)를 뜻한다.
< true
```
좌측값이 true 그리고 우측 값도 true이므로 결과 값이 true가 반환 되었다.

and(그리고)와 또다른 개념으로 or(또는)이 있다.

```js
> 10 < 5 || 10 > 5 ; //여기서 \\는 or(또는)을 뜻한다.
< true
```
좌측값이 false 지만 우측값이 true 이므로 결과가 true가 반환 되었다.

참을 거짓으로 거짓을 참으로 바꿔주는 연산자도 있다.
```js
> !false;
< true

> !true;
< false
```
이러한 성질을 활용해서 다른 자료형을 불 값으로 형 변환 할 수 있다. !연산자를 연달아 두 번 쓰게 된다면 참인 값은 거짓으로 다시 거짓에서 참으로 변환된다.
```js
> !!'Cassandra';
< true
```
'Cassandra'는 String이지만 !을 붙이므로써 boolean으로 바뀌면서 true에서 false로 바뀌었고 다시한번 !을 붙이면서 false에서 true로 바뀐걸 알 수있다.

대부분의 형태들은 불 값으로 변환 했을때 true가 나온다. 하지만 false가 되는 값도 있다. false가 되는 값은 몇 개 없으니 이것만 기억하자!

```js
> !!false; // boolean
< false

> !!''; // String(빈 문자열)
< false

> !!0; // Number
< false

> !!NaN; // NaN
< false

> !!undefined;; // undefined
< false

> !!null; // null
< false
```
<br/>
<br/>

---
# 2.8 undefined와 null

## 빈 값 사용하기
undefined와 null은 값이 비어있다는 것을 표현하는 공통점이 있다.
<br/>
<br/>


1. undefined
```js
> console.log('hello world');
  hello world
< undefined
```
undefined는 보통 반환 할 값이 없을때 나온다. `console.log()`명령어는 console에 무언가를 입력하지만 결과는 없기 때문에 **undefined**가 반환된다. 

```js
> typeof(undefined);
< "undefined"
```
typeof()를 통해 undefined도 자료형이라는 것을 알 수 있다.
<br/>
<br/>

2. null

null은 undefined와 굉장히 유사하지만 큰 차이가 있다.
```js
> undefined == null;
< true

> null === undefined;
< false 

> typeof(null);
< "object"
```
이렇게보면 알 수 있다. typeof()를 통해 자료형을 검사 해보면 undefined는 "undefined"이고 null은 "object"이다. 이것은 원래 버그이나 언어가 만들어진 초창기 실수 때문에 이러한 현상이 발생한다.

