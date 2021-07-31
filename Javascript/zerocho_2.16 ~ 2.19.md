# 2.16 ~ 2.17 반복문 (while, for)
 
반복문이란 말그대로 무언가를 반복하기 위한 것이다. 조건문과 더불어서 가장 많이 쓰이는 문중 하나이다.

## 1) while
```js
// while반복문의 기본 형식
while (조건식){
    (동작문1);
    (동작문2);
    (동작문3);
}
```
반복문은 조건이 만약 참일경우 계속해서 반복된다.
```js
while (true) {
    console.log('hello world');
}
```
위와 같은 코드가 있으면 콘솔창에 무한적으로 'hello world'가 나오게 되고 브라우저가 멈추게 되니까 주의하도록 하자

그럼 어떻게 반복문을 중간에 멈추게 할까?? 답은 변수를 선언하면 된다.
```js
//예시
let k = 1;

while (1 <= 100) {
    console.log('hello world');
    k++;
}
```
여기서 k++는 k+1이다. 그러면 k에서 1씩더하면서 실행을 하게되고 결국 k가 101이 되는순간 조건이 false가 되어 조건이 멈추게 된다.

## 2) for
반복문에는 while문 외에도 for문도 있다.
```js
for (시작;조건식;종료식)
    동작문;

//밑에 예시

for (let k = 1; k < 100; k++)
    console.log('hello world');
```

<br/>
<br/>

---
# 2.18 break와 continue

## 1) break로 반복문 멈추기
break는 반복문을 중간에 멈출때 사용된다
```js
let k = 1;
while (true) {
    if (k === 5) break;
    k++;
}
console.log(k);
//k가 5일때 까지 무한적으로 돌려주다가 k가 5가되면 멈춘다.
```
이것은 주로 어떠한 값을 찾을때 사용한다.

## 2) continue

continue는 특정 구간을 건너뛸때 사용된다.
```js
let k = 0;
while (k < 10) {
    k++;
    if(k % 2 === 0){
        continue;
    }
    console.log(k);
}
```
여기서 k/2의 나머지가 0인 것을 건너 뛰고 결과값이 나온다. 즉, 홀수만 나온다.

<br/>
<br/>

---
# 2.19 중첩된 반복문 사용하기
중첩된 반복문이란 반복문안에 반복문이 있는것으로 심하면 4번까지도 중첩이 된다.

```js
for (let k = 0 ; k <10 ; k++) {
    for (let s = 0 ; s < 10; s++) {
    console.log(k,s) ;
    }
}

// 결과 값

// k = 0 , s = 0 console.log(0,0)
// k = 0 , s = 1 console.log(0,1)
// k = 0 , s = 2 console.log(0,2)
// k = 0 , s = 3 console.log(0,3)
...
// k = 0 , s = 10 조건X
// k = 1 , s = 0 console.log(1,0)
```
이 부분은 직접적으로 한번 노트에 적어가면서 공부 할 필요가 있다.

```js
//세개의 반복문으로도 가능하다.

for (let k = 0 ; k < 10 ; k++) {
    if(k % 2 === 0) continue;
    for(let s = 0 ; s < 10 ; s++) {
        if(s % 2 === 0) continue;
        for(let t = 0 ; t < 10 ; t++) {
             if(t % 2 === 0) continue;
             console.log(k, s, t);
        }
    }
}

// 결과 값
// k == 0 continue
// k == 1, s == 0 continue
// k == 1, s == 1, t == 0 continue
// k == 1, s == 1, t == 1 console.log(k, s, t)
```
다소 복잡하더라도 직접 해보는 것을 권장한다.
