# 1.0 Data Types Of Python
```py
a_string = 'like this'
a_number = 3
a_float = 3.14
a_boolean = False
a_none = None 
```
파이썬은 위와 같이 변수를 생성한다. 자바스크립트와의 큰 차이는 boolean 부분에서 자바스크립트는 첫글자를 소문자로 작성하는 반면 파이썬은 첫글자를 대문자로 하는것을 원칙으로 한다. 그리고 `none`과 같은경우 자바스크립트의 `null`과 가깝다.

그리고 변수명을 작성할시도 자바스크립트랑 차이가 있다.
파이썬은 snake case(_)라는 방식을 자주 사용한다. <br/>ex) super_long_variable

반면,자바스크립트는 camel case라는 방식을 주로 사용한다 <br/>ex) superLongVariable

<br/>
<br/>

---
# 1.1 List in Python

sequence 는 열거 되어있는것이다 sequnce 종류에는 list 와 tuple 이 있다. <br/>
list : days = list 는 [] 를 사용 str 과는 type이 다르다. (변경 가능)

```py 
# 리스트
days = ["mon","tue","wed","thur","fri","sat"]

print("mon" in days) # days 안에 mon이 있는가?
days.reverse() # days 값을 거꾸로함
days.append("sun") # days에 sun이라는 값을 추가
len(days) # days의 길이
days.[n] # days의 n번째 값을 알려줌
```

<br/>
<br/>

---
# 1.2 Tuples and Dicts

- Tuples

list는 안에 내용들을 변경이 가능하다 하지만 tuples는 변경이 불가능하다. 그럼 tuples는 어떻게 사용할까??

간단하다 []대신 ()로 감싸면 된다.

- Dicts

{}로 만든다.
```py
nico = {
"name": "Nico",
"age": 29,
"Korean": True,
"fav_food": ["Kimchi", "Sashimi"]
}

print(nico["name"])

```

-> dictionary 안에 정보를 list, tuple, boolean, number 등 다양한 type으로 저장할 수 있다. 그리고 데이터도 추가할 수있다.

```py
nico = {
"name": "Nico",
"age": 29,
"Korean": True,
"fav_food": ["Kimchi", "Sashimi"]
}

nico["handsome"] = True
```
이렇게 `nico["handsome"] = True`를 추가하면 dictionary에 `handsome : True`가 추가된다. 

<br/>
<br/>

---
# 1.3 Built in Functions

function()은 어떤 행동(기능)을 작성해서 반복해서 할 수 있게 하는 것이다.

https://docs.python.org/3/library/functions.html
이 사이트를 참고하자.
```py
print(): print sth to the console
len(): 길이
function을 combine 할 수 있음
print(len())
-> type을 바꾸게 해주는 것.
int() 정수
bool() boolean
str() string
float() 소수
```
