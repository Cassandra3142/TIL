# 1.4 Creating a Your First Python Funtion

Python에서는 함수를 정의(define or definition)한다고 한다.
```py
def say_hello():
```
이 함수를 정의할 때 채워주는 body는 들여쓰기 혹은 스페이스바로 여백을 만들어주어야 한다.
``` py
def say_hello():
    print('hello')
```

들여쓰기가 없을 시 함수의 바디로써 인정되지 않음.
```py
def say_hello():
print('hello')
```
이렇게 들어쓰기가 되어있지 않으면 함수가 인정 되지 않는다.

함수 출력 시
ex) say_hello() <<<< 여기서 ()가 없으면 출력 X

1. 함수의 body는 들여쓰기가 있어야 함.
2. 함수 출력 시, say_hello() < ()를 써야 함.

<br/>
<br/>

---
# 1.5 Function Arguments

function argument

funtion의 괄호 안에 넣어주는 것을 argument(인수)라고 한다.
```py
def say_hello(who):
    print("hello", who)


say_hello("suzie")
```

who 자리에 valid한 데이터는 다 들어갈 수 있다.

argument를 통해 함수에 인풋을 넣는다고 생각하면 된다.
```py
def plus(a,b):
    print (a+b)


plus (2,5)
```

인수를 설정한만큼 적어주지 않으면 에러가 생긴다.
```py
def plus(a,b)
    print (a+b)

plus (2) 
# error 발생

```
원한다면 default를 정의해 줄 수 있다.
```py
def minus(a,b=0):
    print (a-b)

minus (2)
```

<br/>
<br/>

---
# 1.6 Returns

* print : 콘솔 창에 오로지 결과를 출력하는 것 뿐 그 이상의 기능x

    그래서 print로 출력한 결과값 마지막 NONE(NULL)값이 있었던 것

* return : 함수에 입력(input)되어 계산된 결과 값(return)이 그 함수로 치환되어 출력

    ex) r_plus(2, 3) -> (return) 5

    +Delete function & One time/One value

    -> 나중에 다시 공부 해 볼것

<br/>
<br/>

---
# Keyworded Arguments
```py
def plus(a,b):
return a - b

result = plus(b=30, a=1)
print(result)
```
String 안에 변수를 포함시키고 싶을경우 

format(f)사용:
```py
def say_hello(name, age):
return f"hello {name} you are {age} years old"

hello = say_hello("nico","12")
print(hello)
```
인수가 여러개일 경우, 순서를 기억하기 어렵기 때문에 Keyworded Arguments 를 쓰는것이 좋다.
```py
hello = say_hello(name = "nico", age = "12")
print(hello)
```