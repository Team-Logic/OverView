## 오리엔테이션 + replit 사용법을 알 수 있다.

(수정: 2022/05/06 22:20 - 작성자 범진우)<br>
(활동 예정 일: 2022/05/07)<br>

## 로직 소개

4차 산업혁명 시대에, 중학교에서 1학년까지만 코딩교육을 진행.<br>
심지어 마음껏 원하는 것을 구현하기 힘든, 스크래치만 진행한다는 것은 시대착오적인 교육이라고 생각합니다. 그러나 학교의 교육과정을 바꾸기엔 무리가 있습니다.<br>
따라서 코딩에 관심이 있거나 재능이 있는 학생들에게 코딩을 통한 문제해결 능력을 길러주고.<br>
그 능력을 확장 시켜서, 장기적으론 학업, 인생 전반에 걸쳐 도움이 되게 만들고 싶습니다.<br>
아무래도 아직 코로나의 위협이 산재해 있다 보니, 시간과 실질적인 활동엔 한계가 있겠지만. 목표를 위해 부단히 노력하겠습니다.<br>
그래서 실제 활동 계획에 대해 간단히 소개하자면, 먼저 프로그래밍 언어를 배우고. 이를 통하여 여러 분야에 대한 기초적인 이해를 도모한 후.<br>
프로젝트를 하나 설계하여 발표하는 활동을 하고 싶습니다. <span class="tooltip" title="박병욱 - 로직 자율동아리 신청서">`(출처)`</span><br>

그러하여 로직 구성원들이 <b>문제 해결 능력</b>, <b>사고력</b> 등을 키워<br>
삶의 통찰력을 향상시키고싶습니다.<br>

<b>이것이 우리 로직의 목적입니다.</b><br>

## IDE

IDE는 `Integrated Development Environment - (통합 개발 환경)` 의 약자입니다.<br>
통합 개발 환경이란 여러가지 개발에 필요한 도구들을<br>
GUI `Graphical User Interface - 그래픽 사용자 인터페이스` 로 합친 애플리케이션 입니다.<br>

<span class="tooltip" title="https://www.redhat.com/ko/topics/middleware/what-is-ide">_(출처 - 레드햇 - IDE란?)_</span>

## 클라우드 IDE

클라우드 형태의 IDE 를 말합니다.<br>
프로그래밍을 시작할때<br>

1. 필요 os 및 기기 준비
2. 언어 설치
3. 에디터 설치
4. 디버거 설치
5. ..... 등등

이렇게 복잡한 시작과정을 줄이기 위하여<br>
클라우드 IDE 는 웹브라우저가 접속이 되는 모든 기기에서 실행 가능한 웹 IDE 입니다.<br>
언어를 설치할 필요도 없이 선택만 하면 되기 때문에 로직에서는<br>
개발 환경을 클라우드 IDE 웹 사이트 중 하나인 `repl.it` 채택 하였습니다.<br>

## repl.it 이란

`repl.it` 은 위에서 말하였듯 <b>클라우드 IDE</b> 입니다.<br>
클라우드 IDE 들<br>

1. cloud9
2. koding
3. CloudPebble
4. 구름IDE
5. Repl.it
6. che
7. Github Codespace
8. Stackblitz
9. Gitpod

중 가장 사용하기 적합하다고 판단했기 때문에 로직은 이를 사용합니다.

## repl.it 사용

순서<br>

1. <a href="https://repl.it">repl.it</a> 에 접속한다.
2. 회원가입 진행 
3. 로그인 진행
4. Organizations - Logic 참여
5. 파이썬 Team Repl 생성
6. 간단한 파이썬 코드 <span class="tooltip" title="박병욱 아이디어">`(updown 게임 복붙)`</span> 작성후 실행

## 첫번째 수업 실습 코드 (updown 게임)
```python3
import random

num = random.randint(1, 100)
input_num = 0
count = 0

while input_num != num:
    input_num = int(input("수 : "))

    if input_num > num:
        print("down!")
    elif input_num < num:
        print("up!")

    count += 1

print(f"{count}번 만에 맞추셨습니다!")
print(f"정답은 {num}")
```

## 제출할 것
replit 계정 생성 여부<br>
코드 실습 여부<br>

끝

###### 범진우 
