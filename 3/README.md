# 파이썬의 간단한 문법에 대하여 알 수 있다(2)
## 지난 활동 복습
### 과제 설명과 코드 이해

모범답안 
```py
name = input("name : ")
birthday = int(input("birthday : "))

print(f"내 이름은 {name}이고 생일은 {birthday}야 꼭 기억해줘!")
```

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
사실 bool 변수 형으로 변환하는 경우는 거의 없어 <br>
딱히 의미는 없는 내용이긴 하다.<br>

이렇게 `bool` 타입에 대한 설명을 마치겠다.<br>



## 비교 연산자

비교 연산자는 이름에서 알 수 있는 것 처럼 비교를 하는 연산자 이다.<br>
이게 무슨 소리인지는 지금부터 알아보자<br>

산술 연산자(사칙연산)에 대하여 우리는 배웠다.<br>
사용은 이거와 같다. 하지만 비교 연산자는 우리가 방금 배운 `bool` 타입을 반환한다.<br>

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

더 있지만 우리가 배울건 이정도로 충분하다.<br>
문자열도 가능하다.

```py
print("hello" == "hello") # True
print("hello" != "bye") # True

print("hello" != "hello") # False
print("hello" == "bye") # False
```

물론 문자열도 정수처럼 크다 작다 비교 연산을 할 수 있지만 우리가 배우기엔 좀 어려운 개념이기 때문에 제외하였다.<br>
bool도 너무 예측 가능하여 제외하였다.<br>

## 조건문
코딩이 재밌어지는 첫번째 요소인 조건문이다.<br>
우리가 오늘 지금까지 배운 `bool`과 비교연산자는 지금 배울 조건문의 밑밥이였다.<br>

조건문을 편하게 영어로 if문 이라고 읽기도 한다.<br>
이제부턴 if 문이라고 작성하겠다. <br>

if문은 조건을 충족하면 if문에 딸린 코드를 실행한다.<br>
이게 뭔소리인지는 코드를 보며 이해해보자<br>

```py
a = True
if a:
    print("hello world")
```

자 코드를 뜯어보자<br>
먼저 a 는 True 값을 갖는 bool 형의 변수이다. <br>
if a: 는 만약 a가 True 라면 딸린 코드를 실행한다는 말이고 <br>
실제 이 코드를 실행하면 hello world 가 나오게 된다. <br>

그렇다면 만약 a 가 bool 형태가 아니라면 어떻게 될까? <br>

그런 경우엔 자동으로 bool타입으로 변환해준다.<br>

```py
if 1:
    print("출력 됨")
if 0:
    print("출력 안됨 (절대로)")

if "hi":
    print("출력됨 (빈 문자열이 아니면 무조건 True)")
if "":
    print("출력 안됨 (절대로)")
```

비교연산 또한 bool을 반환하기 때문에 이런게 가능하다.<br>

```py
name = input("당신의 이름 : ")

if name == "범진우":
    print("당신은 로직 운영자 입니다!")
```

여러 응용 가능하다. 계산기도 만들 수 있다.<br>

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

이제 elif 와 else 에 대해서 배울 텐데.<br>
이걸 효과적으로 이해하기 위해 비유를 들어보자.<br><br>

코드가 실행되는 동안에는 여러 상황이 생기는데 이 상황을 자동차라고 생각하고 코드를 고속도로라고 생각하자.<br>
if 문은 톨게이트라고 하자. 하나의 조건에 따라 각 자동차마다 통과하게 할지 말지를 결정하는 것이다.<br><br>

하지만 톨게이트를 계속 띄엄띄엄 설치한다면 차가 계속 멈출 것이다. 그럼 반란이 일어날 수 있기에<br>
이땐 else if 문을 사용하면 된다, 이는 추가적으로 조건을 만들어<br>
톨게이트을 여러번 설치하는 대신, 한 톨게이트에서 여러 조건을 만든다.<br>
(참고로 elif 문은 순차적으로 진행되며, 이전 elif 문이 끝나면 다음 elif 문으로 가게 된다. 모든 elif 문이 끝나면 종료된다.)<br>

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
```
<br>
이렇게 조건을 여러개 추가할 수 있다.<br>
그런데 톨게이트에서 하이패스를 쓰는 차들(if와 elif 조건에 걸리지 않는 경우)에게 마일리지를 준다면 어떻게 해야 할까?<br>
이땐 else 라는 걸 쓰면 된다.<br>
else 는 if와 elif 에 걸리지 않은 경우에 발동된다.<br>
아래 코드를 보면 이해 될 것이다.<br>

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
    print("당신은 외부인입니다.")
    print("꺼져주세요.")
```

## 반복문 while
while의 영단어 뜻은 보통 ~동안 이라는 뜻으로 쓰인다.<br>
파이썬에서도 마찬가지로 조건문이 True 일 동안 특정 문장을 수행한다.<br>
아래의 while문 사용 형식을 보면 이해가 더 잘 될 것이다.<br>
```py3
while #조건문:
    #실행시킬 코드
```
while문은 위와 같은 형식으로 사용하는데 이때 조건문이 True 여야 코드를 반복한다

```py3
a = 0
while a < 10:
    print("10 미만")
    a = a + 1
```
위 코드는 a 값이 10 미만일 동안 "10 미만" 이라는 문장을 출력하고 기존 a 값에 1을 더해준다.<br>
만약 a 값이 10 이상 또는 초과일경우 while 문의 조건문이 False로 실행되지 않는다.<Br>

###### 범진우, 석원민, 박병욱 작성 
