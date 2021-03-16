# 문자열 관련 메소드

- 파이썬의 문자열은 인덱싱과 슬라이싱이 가능하지만 인덱싱으로 원소를 변경할 수 없다. **파이썬에서 문자열은 상수다.**

### replace

- 파이썬은 문자열을 변경할 수 있는 replace함수를 제공한다. 자바와 같이 replaceAll함수는 존재하지 않는다.
- 파이썬의 replace함수는 개수를 인자로 넘겨주지 않으면 매치하는 모든 문자를 변경한다.

```python
text = '123,456,789'

replaceAll = text.replace(",","")
#=> 123456789
replace_once = text.replace(",","",1)
#=> 123456,789
replace_twice = text.replace(",","",2)
#=> 123456789

text2 = "hello world"
replaceHello = text2.replace("hello",'hi')
#=> hi world

text3 = "병건,병건,병건"
result = text3.replace("병건","hello")
#=> hello,hello,hello
```

<br>
<br>

### 문자열 조작

replace 말고 다른 메소드에 대해 알아보자.

- `string.split()`
  - 문자열을 매개변수를 기준으로 분리하여 리스트를 반환한다. 인자가 없는 경우 공백을 기준으로 분리한다.
  - **문자 각각을 리스트의 원소로 바꾸려면, 리스트 컴프리헨션을 사용하자.**
- `'토큰'.join(array)`
  - **문자열 list**를 문자열로 반환한다. 각 원소를 잇는 것은 join의 매개변수로 들어온 것으로 한다.
- `string.rstrip()` 문자열의 오른쪽 공백 삭제
  - 매개변수로 들어온 문자들을 문자열에서 삭제하는 역할도 가능하다. 오른쪽부터 제거하면서 제거할 문자가 아닌경우 동작을 멈춘다.
- `string.lstrip()` 문자열의 왼쪽 공백 삭제
  - 매개변수로 들어온 문자들을 문자열에서 삭제하는 역할도 가능하다. 왼쪽부터 제거하면서 제거할 문자가 아닌경우 동작을 멈춘다.
- `string.strip()` 문자열의 양쪽 공백 삭제
  - 매개변수로 들어온 문자들을 문자열에서 삭제하는 역할도 가능하다. 양 끝부터 제거하면서 제거할 문자가 아닌경우 동작을 멈춘다.

> #### **특수문자 제거**
>
> `string` 모듈의 `punctuation`에는 모든 특수문자가 들어가있다. 특수문자를 제거하려면 `string.punctuation`을 replace나 strip을 이용해서 제거해주면 된다.

<br>
<br>

### 문자열 채우기

- `string.rjust(10)`
  - 문자열을 오른쪽으로 밀고, 왼쪽에 남는 digit만큼 공백을 채운다.
- `string.ljust(10)`
  - 문자열을 왼쪽으로 밀고, 오른쪽에 남는 digit만큼 공백을 채운다.
- `string.center(10)`
  - 문자열을 가운데에 두고, 양쪽 끝에 남는 digit만큼 공백을 채운다.
- `string.zfill(10)`
  - 문자열 왼쪽에 인자로 들어온 수만큼 0을 붙인다.

<br>
<br>

### 대소문자 판별

- `string.upper()`
  - 문자열의 모든 문자를 대문자로 변경
- `string.lower()`
  - 문자열의 모든 문자를 소문자로 변경
- `string.swapcase()`
  - 문자열의 대문자를 소문자로 변경하고, 소문자를 대문자로 변경한다.
- `string.isUpper()`
  - 문자열의 모든 문자가 대문자인 경우 True를 반환, 아니면 False 반환
- `string.isLower()`
  - 문자열의 모든 문자가 소문자인 경우 True를 반환, 아니면 False 반환
- `string.isalpha()`
  - 문자열의 모든 문자가 영어나 한글로만 이뤄진 경우 True를 반환, 아니면 False를 반환
- `string.isdigit()`
  - 문자열의 모든 문자가 숫자인 경우 True를 반환, 아니면 False를 반환
- `string.isalnum()`
  - 문자열의 모든 문자가 숫자 또는 알파벳으로 이뤄진 경우 True를 반환

<br>
<br>

### 매치 판별

- `in` 연산자를 통해 부분 문자열이 존재하는지 확인 가능하다.
- `string.startswith()`
  - 문자열이 매개변수로 입력한 문자열로 시작하면 True를 반환하고 아니면 False를 반환한다.
- `string.endswith()`
  - 문자열이 매개변수로 입력한 문자열로 끝나면 True를 반환하고 아니면 False를 반환한다.
- `string.find()`
  - 문자열에 매개변수로 입력한 문자열이 있는지를 **앞에서 부터** 찾아 인덱스를 반환한다. 여러개인 경우에 제일 앞에 있는 인덱스를 반환한다. 매치되는 문자열이 없으면 `-1`을 반환한다.
- `string.rfind()`
  - 문자열에 매개변수로 입력한 문자열이 있는지를 **뒤에서 부터** 찾아 인덱스를 반환한다. 여러개인 경우에 제일 뒤에 있는 인덱스를 반환한다. 매치되는 문자열이 없으면 `-1`을 반환한다.
- `string.count()`
  - 문자열에 매개변수로 입력한 문자열이 몇 개 등장하는지 개수를 반환해준다.

<br>
<br>

### 주의

- 대부분 문자열 메소드(sort 제외하고)는 새로운 문자열을 반환한다.

```python
def solution(s):
    s = s.lower()
    return s.count('p') == s.count('y')
```
