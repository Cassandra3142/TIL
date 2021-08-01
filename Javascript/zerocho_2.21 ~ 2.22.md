# 2.21 배열 기본

- 객체 (object)

객체(object)는 자료형의 일종으로 다양한 값을 모아둔 또다른 값이다. 객체의 종류로는 배열(array), 함수(function), 배열이나 함수가 아닌 다른 객체로 나눌 수 있다.


<br/>
<br/>

- 배열

```js
const red = '빨강';
const blue = '파랑';
const yellow = '노랑';
const orange = '주황';
```
```js
const color = ['빨강','파랑','노랑','주황']
```
위에 코드랑 아래 코드랑 차이점을 알아보자 

색깔의 종류가 너무 많기 때문에 모든 색깔에 변수 이름을 붙이기 보다는 color라는 const로 묶을 수 있다.

```js
const color = ['빨강','파랑','노랑','주황'];

console.log(color[0]);
console.log(color[1]);
console.log(color[2]);
console.log(color[3]);

// 결과 값

빨강
파랑
노랑
주황
```

위에 코드처럼 색깔을 불러 올 수있다.

배열안에 배열을 넣을 수 있고 배열 안에 변수를 넣을 수 있다.
```js
const arrayOfArray = [[1,2,3],4,5];
arrayOfArray[0]; //[1,2,3]

const a = 1;
const b = 2;
const variableArray = [a,b,3];
variableArray[1]; // b값인 2가 출력
```

<br/>
<br/>

- 요소

배열안에 들어있는 값을 요소라고 한다. 배열에 들어있는 요소의 갯수를 알고 싶으면 배열.length를 해보면된다.
```js
const color = ['빨강','파랑','노랑','주황'];
console.log(color.length);

//결과 값
4
```
위에 코드를 응용하게 된다면 배열안에 요소를 찾을 수도 있다.
```js
const color = ['빨강','파랑','노랑','주황'];
console.log(color[color.length -1]); // console.log(color[4-1])

//결과 값
주황
```
이런식으로 요소의 뒷부분 부터 차례대로 찾을 수 있다.

- 배열안에 요소 넣기
```js
const color = ['빨강','파랑','노랑','주황'];
color[4] = '보라'
console.log(color)

//결과 값

['빨강','파랑','노랑','주황','보라'];
```
하지만 이렇게 추가하다보면 배열의 길이를 알아야 하기 때문에 다른 방법을 사용해 보자
```js
const color = ['빨강','파랑','노랑','주황'];
color[color.length] = '보라';
console.log(color)

// 결과 값

['빨강','파랑','노랑','주황','보라'];
```
근데 보통 배열에 값을 추가할때는 `배열.push()`를 많이 사용한다
```js
const color = ['빨강','파랑','노랑','주황'];
color.push() = '보라';
console.log(color)

//결과 값

['빨강','파랑','노랑','주황','보라'];
```
만약 배열 제일 앞에 요소를 추가하고 싶다면 어떻게 해야 할까? 이러한 경우 `배열.unshift`라는 기능이 있다.
```js
const color = ['빨강','파랑','노랑','주황'];
color.unshift('보라');
console.log('color')

// 결과 값

['보라','빨강','파랑','노랑','주황'];
```
<br/>
<br/>

---
# 2.22 배열 메서드 (수정, 조회)

- 배열에서 요소 수정하기
```js
const color = ['빨강','파랑','노랑','주황'];
color[3] = '보라'
console.log(color)

//결과 값

['빨강','파랑','노랑','보라'];
```
위에처럼 수정하고 싶은 곳을 지정하여 바꾸면 된다.

<br/>
<br/>

- 배열에서 요소 제거하기

배열.pop()을 사용하면 배열의 마지막 요소를 제거할 수 있다.
```js
const color = ['빨강','파랑','노랑','주황'];
color.pop();
console.log(color)

//결과 값

['빨강','파랑','노랑'];
```
반대로 `배열.shift()`를 사용하여 첫번째 요소를 제거 할 수 있다.

```js
const color = ['빨강','파랑','노랑','주황'];
color.shift();
console.log(color)

//결과 값

['파랑','노랑','주황'];
```
그럼 중간에 있는 요소는 어떻게 제거 해야 할까?? `배열.splice()`를 사용하면 된다.

```js
배열.splice(지우고싶은 인덱스, 그 인덱스로부터 몇개를 지울지);

// 예시

const color = ['빨강','파랑','노랑','주황'];
color.splice(1,1);
console.log(color)

//결과 값

['빨강','노랑','주황'];
```
만약 `배열.splice()`에 값을 하나만 넣으면 어떻게 될까??
```js
const color = ['빨강','파랑','노랑','주황'];
color.splice(1);
console.log(color)

//결과 값

['빨강'];
```
지정해둔 요소에서 뒤에 값들을 다 지워버린다.

`배열.splice()`로 배열의 요소를 지우고 그 자리에 다른 요소를 추가 할 수있다.
```js
const color = ['빨강','파랑','노랑','주황'];
color.splice(1,1,'보라');
console.log(color)

//결과 값

['빨강','보라','노랑','주황'];
```

- 배열에서 요소 찾기

배열에 특정 요소가 있는지 찾는거는 `배열.includes()`기능을 사용하면 된다.

```js
const color = ['빨강','파랑','노랑','주황'];
const a = color.includes('빨강');
const b = color.includes('보라');
console.log('a')
console.log('b')

//결과 값

true
false
```
만약 배열안에 있으면 true 없으면 false가 출력 된다.

`배열.indexOf()와 배열.lastIndexOf`를 통해찾고싶은 값이 몇번째 인덱스에 있는지도 알 수 있다.
```js
const color = ['빨강','파랑','노랑','주황'];
const a = color.indexOf('파랑');
const b = color.lastIndexOf('노랑');
const c = color.indexOf('보라');
console.log('a')
console.log('b')
console.log('c')

//결과 값
1
1
-1
```
indexOf는 앞에서 부터 순서대로 찾고, lastIndexOf는 뒤에서 부터 찾는다, 만약 값이없으면 -1 이 출력 된다.

<br/>
<br/>

- 배열 반복하기

배열은 값을 나열한 것이기 때문에 반복문과 같이 사용하는 경우가 많음 while이나 for 둘다 사용 가능
```js
const color = ['빨강','파랑','노랑','주황'];
    let k = 0
    while(k < color.length) {
        console.log(target[k])
        k++
    }

// 결과 값

빨강
파랑
노랑
주황
```

```js
const color = ['빨강','파랑','노랑','주황'];
for( k = 0; k < color.length; k++){
    console.log(color[k]);
}

// 결과 값
빨강
파랑
노랑
주황
```

