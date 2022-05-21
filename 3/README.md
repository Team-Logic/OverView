# 파이썬의 간단한 문법에 대하여 알 수 있다(2)
## 지난 과제 설명
모범답안
```py
name = input("name : ")
birthday = int(input("birthday : "))

print(f"내 이름은 {name}이고 생일은 {birthday}야 꼭 기억해줘!")
```

## 지난 활동 요약

문자열 입력 받기
```py
a = input()
```

타입 확인과 타입 종류와 타입변환

```py
print(type(name)) # str(ing) 스트링
print(type(birthday)) # int(eger) 인트

print(type(str(birthday))) # str(ing) 스트링
print(type(int(name))) # 에러 (숫자범위의 문자가 아닌 문자를 int로 바꿀 수 없다.)
```

변수와 문자 같이 출력
```py
print(f"내 이름은 {name}이고 생일은 {birthday}야 꼭 기억해줘!") # 괄호와 (큰)따옴표 사이에 f를 넣고 넣고 싶은 변수를 중괄호 안에다 넣는다.
```

## 새로운 타입 bool 

`bool`은 `boolean` 이라고도 부르고 한글로 불, 불리언 이라고 발음한다.<br>
논리 자료형 으로도 불리는 `bool` 은 영국의 수학자이자 논리학자인 George Boole(조지 불) 의 이름에서 따온것이다.<br>

### bool 이 담는 변수의 형태
`int`는 정수를 `str`은 문자열 을 담는것 처럼<br>
`bool`은 참과 거짓을 담는다.<br>

```py
a = True
b = False

print(type(a)) # bool
print(type(b)) # bool
```

이때 중요한점은 `a = "True"` 와 다르다는 것 이다.<br>
`"True"`는 문자열로 그냥 True이지만 (큰)따옴표를 붙이지 않은 `True, False`는 참과 거짓을 나타내는 bool 타입이다.<br>

```py
a = "True"
b = "False"

print(type(a)) # str
print(type(b)) # str
```

사용할때 주의할 점은 `True, False` 이렇게 대문자로 시작을 해줘야 파이썬이 `bool` 이라는걸 이해한다.<br>

```py
a = True
b = False

# 이런식으로 값을 쉼표로 구별해주면 자동으로 띄어쓰기를 해주며 출력된다.
print(a, b) # 출력값 : True False
```

### bool의 타입변환
(type(N) = int)
정수 N은 문자열 "1" 로 변환할 수 있고<br>
문자열 "N"은 정수 N으로 변환할 수 있다고 지난시간에 배웠다.<br>

그럼 정수, 문자열 을 `bool`로 또는 `bool`을 정수, 문자열로 변환할 수 있을까?<br>
놀랍게도 가능하다.<br>

### `bool`을 `str`, `int` 로 변환<br>

```py
a = True
print(str(a)) # "True" 문자열로 된 "True"를 출력한다.
print(int(a)) # 정수 1 을 출력한다. (이유는 후에 설명)

b = False
print(str(b)) # "False" 문자열로 된 "False"를 출력한다
print(int(a)) # 정수 0 을 출력한다. (이유는 후에 설명)
```

먼저 문자열로 변환하는 것 부터 살펴보겠다.<br>
`True`를 문자열로 변환하니 `"True"`가 `False`를 문자열로 변환하니 `"False"`가 출력되었다. 충분히 예상 가능한 결과였다.<br>

그러면 정수로 변환한 결과는 왜 저렇게 나왔을까?<br>
`True`를 정수로 변환하니 `1`이 `False`를 정수로 변환하니 `0`이 나왔다.<br>
무언가 익숙한 두 수로 보여진다.<br> 

0과 1은 대부분 알다시피 이진법이다 컴퓨터에서 이런 수 체계를 사용하는 이유를 간단하게 설명하자면<br>
전기가 흐른다 = 1, 전기가 흐르지 않는다 = 0 으로 컴퓨터에서 쉽게 표현할 수 있기 때문에<br>
0과 1을 사용하는 것 이다.<br>

정리하자면 컴퓨터에서 전기가 흐른다는 `True`를 뜻하고 이것을 수로 표현하면 `1`이다. 반대로는 `False`이고 `0`인 것이다.<br>
그래서 `True`를 정수로 변환하면 `1` `False`를 정수로 변환하면 `0`이 나오는 것이다.<br>

### `str`, `int`를 `bool` 로 변환
bool을 str, int로 변환하는 것 보다는 복잡하지만 매우 쉽다.<br>

우리는 위의 과정을 잘 알고 있기 때문에 간단히 코드로만 설명하겠다.<br>

```py
# 0이 아닌 모든 정수는 True를 반환한다.
print(bool(0)) # False
print(bool(1)) # True

# 빈 문자열이 아닌 모든 문자열은 True를 반환한다.
print(bool("")) # False
print(bool("False")) # True
print(bool("fjoqfoij")) # True
```
이렇게 `bool` 타입에 대한 설명을 마치겠다.<br>

## 비교 연산자

비교 연산자는 이름에서 대략적으로 추측할 수 있는 것처럼 옳고 그름을 비교해주는 연산자이다<br>
이게 무슨 소리인지는 지금부터 알아보자<br>

산술 연산자(사칙연산)에 대하여 우리는 배웠다.<br>
사용은 산술 연산자와 같다. 하지만 비교 연산자는 옳고 그름을 가르기 때문에 우리가 방금 배운 `bool` 타입을 반환한다.<br>

비교 연산자의 사용법
```py
print(1 == 1) # True (1과 1은 같다)
print(1 != 2) # True (1과 2는 다르다)
print(1 < 2) # True (1보다 2가 크다)
print(2 > 1) # True (2보다 1이 작다)
print(1 <= 2) # True (1보다 2가 크거나 같다)
print(2 >= 1) # True (2보다 1이 작거나 같다)

print(1 == 2) # False (1과 2는 같다)
print(1 != 1) # False (1과 1은 다르다)
print(1 > 2) # False (1보다 2가 작다)
print(2 < 1) # False (2보다 1이 크다)
print(1 >= 2) # False (1보다 2가 작거나 같다)
print(2 <= 1) # False (2보다 1이 크거나 같다)
```

더 많은 비교 연산자가 존재하지만 이정도만 알아도 좋다.<br>
문자열도 비교 연산자로 비교가 가능하다.

```py
print("hello" == "hello") # True
print("hello" != "bye") # True

print("hello" != "hello") # False
print("hello" == "bye") # False
```

물론 문자열도 정수처럼 크다 작다 비교 연산을 할 수 있지만 우리가 배우기엔 좀 어려운 개념이기 때문에 제외하였다.<br>
bool도 너무 예측 가능하여 제외하였다.<br>

## 논리 연산자
논리 연산자는 비교연산자 처럼 bool 값을 반환하는 연산자 이다.<br>
논리 연산자의 대표 종류로는 `And`, `Or`, `Not` 있다 각각의 사용법을 알아보자<br>

### And
`And` 는 두 bool 값이 모두 참일때 참을 반환한다. 표를 한번 봐보자<br>

| A | B | Result |
| ---- | ---- | ---- |
| True | True | True |
| True | False| False|
| False| False| False|
| False| True | False|

A와 B 둘다 True일때만 True의 값을 반환하는걸 알 수 있다.<br>
파이썬에서는 이렇게 표현한다.<br>

```py
print(True and True) # True
print(True and False) # False
print(False and False) # False
print(False and True) # False
```

### Or
`Or` 은 두 bool 값 중 하나 이상이 참일때 참을 반환한다.<br>

| A | B | Result |
| ---- | ---- | ---- |
| True | True | True |
| True | False| True |
| False| False| False|
| False| True | True |

```py
print(True and True) # True
print(True and False) # True
print(False and False) # False
print(False and True) # True
```

### Not
`Not`은 bool 값을 부정한다.<br>

| bool | Result |
| ---- | ---- |
| True | False|
| False| True |

```py
print(not True) # False
print(not False) # True
```

### 비교 연산자와의 응용

```py
a = input("약관의 동의 하십니까? : ")

print(not (a=="No" or a=="no" or a=="아니요" or a=="아뇨")) # a가 Yes라면 True No라면 False 를 출력 
```

## 조건문
코딩이 재밌어지는 첫번째 요소인 조건문이다.<br>
우리가 오늘 지금까지 배운 `bool`과 비교연산자는 오늘의 핵심인 조건문을 배우기 위한 디딤돌이라고 봐도 된다.<br>

조건문을 편하게 영어로 if문 이라고 읽기도 한다.<br>

조건문은 조건을 충족하면 밑의 코드를 실행한다.<br>
아래의 코드를 보며 천천히 이해해 보자<br>

```py
a = True
if a:
    print("hello world")
```
위 코드를 보면 대략적으로 알겠듯이
```py3
if #bool:
    #bool 이 True 라면 실행될 코드
```
이러한 형태이다.<br>
진행자의 설명이 이를 더 자세하게 설명 해 줄 것이다.<br>
`if`는 True와 False의 값만 받는다. 만약 True와 False 즉 bool타입이 아닌 값을 받았을때는 자동으로 bool타입으로 변환한다.<br>

비교연산자 또한 bool을 반환하기 때문에 이런게 가능하다.<br>

```py
name = input("당신의 이름 : ")

if name == "범진우":
    print("당신은 로직 운영자 입니다!")
```

`else`는 위 if의 조건이 거짓일때 발동된다. 즉 단독으로 사용이 불가하다.<br>

```py
if name == "범진우":
    print("당신은 로직 운영자 입니다!")
else:
    print("당신은 로직 운영자가 아닙니다.")
```

`elif`는 if랑 사용법이 같다 하지만 위 if또는 위 elif의 조건이 거짓일때 순차적으로 발동된다. 즉 단독으로 사용이 불가하다.<br>
```py
if name == "범진우":
    print("당신은 로직 운영자 입니다!")

elif name == "박병욱":
    print("당신은 힙스터 입니다!")

elif name == "석원민":
    print("당신은 돌 입니다!")

elif name == "송호진":
    print("당신은 딸기 입니다!")

elif name == "이석훈":
    print("당신은 우는고양이 입니다!")

elif name == "이예준":
    print("당신은 과일 입니다.")

else:
    print("당신은 외부인 입니다.")
```

int 타입으로 이렇게 응용이 가능하다.<br>

```py
money = int(input())

if money >= 10000:
    print("택시를 타고 가시오.")
elif money >= 5000:
    print("버스를 타고 가시오.")
elif money >= 2500:
    print("지하철을 타고 가시오.")
else:
    print("걸어가시오")
```

위에서 말한 것 처럼 bool 타입이 아닌것을 넣으면 bool 타입으로 자동으로 변환한다.<br>

```py3
# True = 1, False = 0(bool 타입 부분 참조)
if 1:
    print("출력 됨")
if 0:
    print("출력 안됨 (절대로)")

if "hi":
    print("출력됨 (빈 문자열이 아니면 무조건 True)")
if "":
    print("출력 안됨 (절대로)")
```

### pass
코딩을 하다 보면 이런식의 코드를 작성할 때가 생긴다.<br>

```py
a = 10
if a == 10:

else:
    print("a는 10이 아닙니다.")
```

물론 비교연산자의 `!=`를 쓰면 해결 되지만 저런식으로 코드를 쓴다는 가정하에 실행해보면 파이썬 문법 오류가 난다.<br>
그 이유는 첫번째 조건인 `if a == 10:`에 아래 블록에 코드가 존재하지 않기 때문인데 우리는 저기서 실행시킬 코드가 없고<br>
그냥 아래로 넘어가는걸 원하기 때문에 그럴때는 `pass`를 적어주면 된다.<br>

```py
a = 10
if a == 10:
    pass
else:
    print("a는 10이 아닙니다.")
```

`pass`는 정말 아무것도 실행하지 않는 코드이다 어디에서든 쓸 수 있고 저런식으로 블록에 어쩔 수 없이 공백이 있을때<br>
또는 공동 개발을 하면서 상대방에게 이부분에 코드를 넣어달라고 요청 할 수 있다.<br>

```py
a = 10
if a == 10:
    pass # 이 부분에 a가 10일때 축하 메세지를 띄워주는 코드를 작성해 주세요.
else:
    print("a는 10이 아닙니다.")
```

이런식으로 말이다.<br>

## 반복문 while
while의 영단어 뜻은 보통 ~동안 이라는 뜻으로 쓰인다.<br>
파이썬에서도 마찬가지로 bool값이 True 일 동안 특정 문장을 수행한다.<br>
아래의 while문 사용 형식을 보면 이해가 더 잘 될 것이다.<br>
```py3
while #bool:
    #위 bool이 True(성립) 이라면 반복 시킬 코드
```
while문은 위와 같은 형식으로 사용한다.<br>
아래 예제를 보자

```py3
a = 0
while a < 10:
    print(f"{a} = 10 미만입니다")
    if a == 9:
        print("마지막 숫자입니다")
    a = a + 1 
```
위 코드는 a 값이 10 미만일 동안 "10 미만" 이라는 문장을 출력하고 기존 a 값에 1을 더해준다.<br>
만약 a 값이 10 이상 또는 초과일경우 while 문의 비교 연산자가 반환하는 bool값이 False임으로 실행되지 않는다.<Br>
위 코드를 실행해보면 0 ~ 9 까지는 10 미만임을 성립함으로 "10 미만" 이라는 문장이 10번 실행될 것이다.<br>
조금 더 쉽게 표로 알아보자면<br>
| 변수 a | 비교 연산  | bool 값 | 수행할 문장                        | while 문 상태 |
| ------ | ------- | -------------- | ---------------------------------- | ------------- |
| 0      | 0 < 10  | True           | 0 = 10 미만 입니다                 | 반복          |
| 1      | 1 < 10  | True           | 1 = 10 미만 입니다                 | 반복          |
| 2      | 2 < 10  | True           | 2 = 10 미만 입니다                 | 반복          |
| 3      | 3 < 10  | True           | 3 = 10 미만 입니다                 | 반복          |
| 4      | 4 < 10  | True           | 4 = 10 미만 입니다                 | 반복          |
| 5      | 5 < 10  | True           | 5 = 10 미만 입니다                 | 반복          |
| 6      | 6 < 10  | True           | 6 = 10 미만 입니다                 | 반복          |
| 7      | 7 < 10  | True           | 7 = 10 미만 입니다                 | 반복          |
| 8      | 8 < 10  | True           | 8 = 10 미만 입니다                 | 반복          |
| 9      | 9 < 10  | True           | 9 = 10 미만 입니다<br>마지막 숫자입니다 | 반복          |
| 10     | 10 < 10 | False          | 조건 판단 결과가 False 임으로 없음     | 종료          |
  
이렇게 볼 수 있다.  

당연하게도 bool 값이 True일때 무한히 반복하기 때문에<br>
이렇게 무한반복 코드를 적을 수 있다.<br>

```py
while True:
    print("무한반복")

while 1: # 1을 bool 타입으로 변환하면 True이다.
    print("무한반복")
```

그리고 역시 값이 False 일때는 코드가 시작조차 되지 않는다.<br>

```py
while False:
    print("실행 안됨")
```

## 과제
자신의 생일을 맞추는 생일 맞추기 프로그램을 만들어 보자.<br>
난이도: ⭐️⭐️⭐️⭐️(but 조건을 잘 읽어보면 충분히 만들 수 있다!)
### 과제 조건
1. 숫자는 int타입 4자리 숫자로 받아올 것(11월 24일 -> 1124)<br>
2. 유저에게 게임을 시작할까요? 라는 질문의 답을 받아와 반복문으로 사용할 것<br>
3. `while` 문과 `if` 문을 사용할 것(while, if, else, elif 최소 1번 사용)<br>
4. 생일에 근접한 값이면 아까워요! 를 출력하고 생일에 근접하지 않으면 틀렸습니다를 출력할 것(생일에 근접한 값의 기준은 오차범위 ±2)<br>
4-1. 쉽게 말하자면 내 생일이 1124이면 유저가 1122~1126 사이의 값을 입력하면 아깝습니다를 출력(정답 제외)<br>
5. 생일이 아니거나 네자리 이상의 숫자 `예외 경우`엔 네자리 숫자로 입력해주세요 라는 문장을 출력할 것<br>
6. 정답을 입력했으면 축하해주는 문장을 출력하며 `break`으로 코드를 종료할 <br>
7. 포기하지 말 것<br>
8. 다음주 토요일(5/28) 이전까지 제출할 것<br>
    
    
    
###### 범진우, 석원민 작성
