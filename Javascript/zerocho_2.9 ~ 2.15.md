# 2.9 변수 선언하기 (let)
프로그램을 만들 때 잠깐 동안 특정한 값을 저장해야 하는 상황이 발생하는데, 이때 사용하는 것이 변수이다.

```js
let americano = 3000;
let caffelatte = 4000;
let total = 3000 + 4000;
```
이라고 선언을 하고 console에 선언한 변수를 입력한다면 저장된 값이 출력된다.
```js
> console.log(americano);
  3000
< undefined

> console.log(caffelatte);
  4000
< undefined

> console.log(total);
  7000
< undefined
```
지금까지는 간단한 숫자를 저장을 했지만 만약에 복잡한 숫자를 저장한다면 많이 유용하다
```js
let number = 9606053142;
```
만약 이렇게 복잡한 숫자를 변수선언 없이 계속해서 사용한다고 생각한다면 매번 저 숫자를 입력 하지만 변수를 선언했기 때문에 number만 입력해도 9606053142라는 숫자가 나오게 될 것이다.


```js
> let empty; let empty
// 만약 이렇게 같은 변수를 같은 줄에 선언을 한다면 Error가 발생한다.
```
따라서 변수명이 겹치지 않도록 주의를 해야한다.
<br/>
<br/>

---
# 2.10 변수명 짓기

변수명을 지을때 직관적으로 어떤 역할을 하는지 알아보기 쉽게 지어야 한다. 그리고 변수명은 한글로도 지을 수 있고 키보드에 존재하는 특수문자 중에서는 $,_만 쓸 수 있다.

```js
> let 한글 = '세종대왕';
< undefined

> 한글
< "세종대왕"

> let $_ = 'hello';
< undefined

> $_
< "hello"
```

그리고 변수명을 지을때 숫자도 사용할 수 있다. 단, 숫자가 첫 글자면 안된다.

```js
> let banana2 = 'banana';
< undefined

> banana2
< "banana"

> let 2banana = 'banana';
< Error
```

변수명을 지을 때 띄어쓰기도 안된다. 하지만 이러한 점을 보완하기위해 암묵적인 방법이 존재한다.

```js
> let Cassandra is babo = 'babo';
< Error

> let CassandraIsBabo = 'babo';
< undefined

> CassandraIsBabo 
< "babo"
```
띄어쓰기 대신 띄어쓰기 하는 부분을 대문자로 바꾸게 되어 띄어쓰기를 구별한다.

<br/>
<br/>

---
# 2.11 변수 수정하기

변수를 바꾸는 방법에 대하여 알아보자.
```js
> let change = '바꿔라';
< undefined

> change
< "바꿔라"

> change = '바꿨다';
< "바꿨다"

> change
< "바꿨다"
```
변수 안에 있는 값을 비우는 방법

```js
> change = null;
< null

> change = undefined;
< undefined
```
null이나 undefined 둘다 변수값을 비울수 있다 하지만 **null을 쓰는 것을 추천한다**

왜냐하면 undefined는 기본값 역할을 하기때문에 undefined를 쓴다면 의도적으로 비웠다는것을 모르지만 null을 쓴다면 의도적으로 비웠다고 파악하기 쉽기 때문이다.

```js
// 여기서 부터는 예시이다.
> let k = '111'; // 변수k의 값을 지정
< undefined

> k = null; // 변수를 비웠다.
< null

> k // k를 선언하면 당연히 비어있기 때문에 null이 나온다.
< null // 이런식으로  null을 써서 누군가 의도적으로 비워 놨다고 알릴 수 잇다.

> k = undefined; // k를 undefined로 비워보자
< undefined

> k
< undefined // 이 값은 기본값인 undefined로 선언 되었기 때문에 의도적으로 비워 놓은 값인지 아니면 선언을 하지 않은 값인지 알 수 없다.
```

<br/>
<br/>

---
# 2.12 변수 활용하기

```js
> let number = 5;
< undefined

> number = number + 4;
< 9
```
여기서 왜 이런 식이 나오는지 납득이 안되는 사람들이 있을 것이다. 하지만 자바스크립트에서 = 는 같다가 아닌 대입이다.

```js
a = b  // 이것은 b를 a로 대입하는 것이다.
a == b // 값은 비교하지만 자료형은 비교하지않는다.
a === b // 값과 자료형 둘다 비교한다.
```

```js
> number = number + 4;
< 9

> number += 4; 
< 9 
//즉 위아래 식이 같음 
```
위와 같이 두개의 방법이 있으니 적절히 활용 할 것.

<br/>
<br/>

---
# 2.12 const와 var
let 외에도 변수를 선언하는 예약어로 const와 var가 있다.

## 1. const

const는 상수(constant)를 줄인말이다. 상수란 변하지 않고 같은 값을 가지는 수라고 한다.

```js
> const 상수 = "변하지 않음";
< undefined

> 상수 = "변해라";
< Uncaught TypeError : Assignment to constant variable.
```
위의 결과처럼 const는 변경할 수 없다.

## 2.var

var이란 variable의 줄인말이다. 예전에는 많이 사용했지만 다소 이해하기 어려운 특성이 존재하기 때문에 const와 let을 많이 사용하고 있다. 다만, 과거에 작성된 코드에서 많이 사용하므로 var의 특성은 알아야 한다.

```js
// 전반적인 것은 let과 거의 동일하나 차이점이 두가지 있다.

> var 변수 = '선언';
< undefined

> var 변수 = '다시 선언 할 수 있다.';
< undefined
```
```js
> let 변수 = '선언';
< undefined

> let 변수 = '다시 선언 할 수 있다.';
< Uncaught SyntaxError : Identifier 'variable' has already been declared
```
위와같이 let과 var은 재선언할때 차이를 보이고 또다른 차이점으로서

```js
> var let = 'const';
< undefined
```
var은 자바스크립트의 예약어인 let, const, undefined, null 등등을 변수로 사용할 수 있는데 만약 이런 예약어들을 변수로 사용한다면 코드를 작성할때 많이 햇갈릴 수도 있다.

```js
> let let = 'const';
< Uncaught SyntaxError : Identifier 'let' has already been declared
// let같은 경우 예약어를 변수로 쓰면 오류가 발생.
```
var대신 let을 쓰게된다면 위와 같은 상황을 막을 수 있다.

<br/>
<br/>

---
# 2.13 조건문(if)

조건문이란 주어진 조건에 따라 코드를 실행하거나 실행하지 않는 문입니다.

```js
if (조건식){
  동작문
}

// 예시

> if (true){
  console.log("if문");
  }

  if문

< undefined

> if (false){
  console.log("실행x");
}
< undefined
```
조건문 은 위와 같은 형태로 이루어 진다.

<br/>
<br/>

---
# 2.14 else, else if, switch

## 1) else를 사용하여 두 방향으로 나누기

만약 조건식이 true일때 a, false일때 b를 출력하고 싶다면 어떻게 해야 할까?

```js

if (조건식) {
  동작문;
} else {
  동작문;
}

// 예시

if (true) {
  console.log("a");
} else {
  console.log("b");
}
```

## 2) else if를 사용하여 여러방향으로 나누기

```js
if (조건식) {
  동작문;
} else if(조건식){
  동작문;
} else {
  동작문;
}

//예시

const rank = 2;
if (rank === 1) {
  console.log('금메달');
} else if (rank === 2) {
  console.log('은메달');
} else if (rank === 3){
  console.log ('동메달');
} else {
  console.log('다음기회에');
}

//이렇게 코드를 친다면 console에 은메달이 출력 될 것이다.
```
## 3) switch문
조건문에는 ifans dhldpeh switch문이 있습니다. if문과 swith문은 조건을 충족할 때 실행된다는 공통점도 있지만, 차이점도 있다.

```js
switch(조건식) {
  case 비교조건식 : 
    동작문;//조건식과 비교조건식이 같으면 동작문을 실행한다.
}

// 예시

let value = 'A';
  switch(value) {
    case 'A' :
      console.log('A');
  }
  //value랑 비교조건식 'A'가 같으므로 console.log가 실행한다.
  ```

if문과 switch문의 차이점이 있다.

```js
const rank = 2;

if (rank === 1) {
  console.log('금메달');
} else if (rank === 2) {
  console.log('은메달');
} else if (rank === 3){
  console.log ('동메달');
} else {
  console.log('다음기회에');
}
// 이 상황에서 console에 '은메달'이 출력 된다.

const rank = 2;

switch(rank) {
  case 1 :
    console.log('금메달');
  case 2 :
    console.log('은메달');
  case 3 : 
    console.log('동메달');
  default : 
    console.log('다음기회에');
}
// 이러한 상황에서는 '은메달','동메달','다음기회에' 셋다 출력이 된다. 즉, 일치 하는 부분 아래로 쭉 출력이 된다는 것이다.

switch(rank) {
  case 1 :
    console.log('금메달');
    break;
  case 2 :
    console.log('은메달');
    break;
  case 3 : 
    console.log('동메달');
    break;
  default : 
    console.log('다음기회에');
}
// 이렇게 한다면 '은메달'만 출력이 될 것이다.
```
<br/>
<br/>

---
# 2.15 조건부 연산자 (삼항 연산자)

if문과 switch문 외에도 분기 처리에 사용하는 식이 있다. 이를 조건부 연산자 (삼항 연산자)라고 한다. 
```js
조건식 ? 참일때 식 : 거짓일 때 식

//예시

> 5 > 0 ? '참입니다.' : '거짓입니다.';
< "참입니다."
```
위처럼 표현 할 수 있다.

조건부 연산자도 중첩해서 사용 할 수 있다. 하지만 가독성을 위해 ()로 감싸주면 가독성이 더 좋을 것이다.

```js
let c1 = true;
let c2 = false;
let value = c1 ? (c2? '둘다 참' : 'c1만 참') : 'c1이 거짓';

console.log(value);
// 이렇게 된다면 'c1만 참'이 출력 될 것이다.
```

조건부 연산자를 잘 구별하는 방법은 **들여쓰기**를 잘 활용하면 좋다

```js
let value = c1
  ? c2
    ? '둘다 참'
    : 'c1만 참'
  : 'c1이 거짓'
//들여쓰기를 활용한 방법
```


