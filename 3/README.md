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
이렇게 `bool` 타입에 대한 설명을 마치겠다.<br>

## 비교 연산자


