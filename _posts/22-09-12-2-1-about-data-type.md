---
title: 제2장 자료형
author: 한지훈
date: 2022-09-12
category: Type
layout: post
---

### 제1절 자료형이 중요한 이유

대부분의 프로그래밍 언어에서는 자료형을 중요시 하게 되며, 처음 프로그래밍을 학습할 때 자료형은 꽤나 지루한 학습의 과정이 된다. 이것은 자료형을 왜 배우는지에 대해서 정확하게 인지하지 못한 채 학습을 진행하기 때문에 발생한다. 몇 가지 새로운 지식과 예시를 통하여 자료형이 왜 중요한 지에 대해서 알아보도록 하자.

#### 자료형을 사용하는 이유

자료형은 다양한 곳에서 사용된다. 그것이 사용자가 직접 사용을 하든 프로그램이 자체적으로 이용을 하든 말이다. 파이썬에서는 변수에 할당되는 자료에 따라서 자동으로 형변환(Casting) 과정이 진행되므로, 그 중요도는 다소 낮아지지만, 앞으로의 학습을 위해서 이를 짚고 넘어가도록 한다.

몇 가지의 이유는 있지만, 가장 먼저 소개할 사항은 생각보다 간단하다. 효율성을 측면이다. 우리는 앞단에서 변수를 상자에 비교한 바 있다. 만약 아주 조그마한 사물을 거대한 상자에 보관하게 된다면 공간을 낭비하는 셈이 된다. 컴퓨터에서 데이터를 저장하는 메모리 공간의 효율적인 사용을 위하여 다양한 크기의 자료형을 만들어두고 이를 사용하게 되는 것이다.

공간의 효율성과 더불어 연산에서의 효율성도 보장할 수 있다. 소수점이 있는 실수의 계산을 생각하여 보자. 초등학교 등의 저학년 과정에서 우리는 소수점이 있는 계산을 할 때 소수점이 없는 형태로 먼저 계산을 한 뒤 자릿수에 따라서 소수점을 맞게 다시 찍는 과정을 통하여 연산을 진행하였다. 컴퓨터가 실수를 표현할 때는 이처럼 소수점을 고정하지 않고 그 위치를 나타내는 수를 별도로 표기하여 저장하는 부동소수점(浮動小數點, floating point) 방식으로 실수를 표현하게 된다. 여기서 부동은 고정되지 않고 물에 둥둥 떠서 부유(浮遊)하며 움직(動)이는 모습을 나타내는 단어이다.

부동소수점의 예시처럼 자료의 형태에 따라서 저장하는 방식도 변경되며, 이를 연산하는 방법도 다르게 된다. 즉 자료형에 따라서 각 변수의 저장 공간을 효율적으로 관리할 수 있으며 연산을 위한 알고리즘도 최적화할 수 있다는 것이다.

파이썬에서는 해당하지 않지만 다른 프로그램에서는 각 자료의 저장 공간, 즉 변수를 할당할 때 자료형을 할당하는 정형이라는 과정을 거친다. 이러한 정형 과정을 거치게 되면 상대적으로 명령의 안전성을 보장할 수 있다. 예를 들어보자. 숫자와 글자 사이의 사칙연산을 우리는 쉽게 생각할 수 없다. 물론 파이썬 등 여러 프로그래밍 언어에서는 이러한 산술방식도 유효하지만, 기존의 사고 체계에서는 사실 받아들이기 어려운 오류이다. 이처럼 자료형을 잘 활용한다면 무의미한 연산 및 오류가 발생할 여지가 있는 명령을 실행하기 전에 감지할 수 있게 된다.

우리가 배울 파이썬은 이러한 자료형을 명시하지는 않는다. 변수에 자료가 할당될 때마다 자동으로 그 자료형을 변환하는 과정을 거치기 때문이다. 다만 주의할 점은 자료형의 명시여부가 프로그래밍 언어의 우월성을 나타낸다고 보기는 어렵다. 저마다의 장단점을 가지고 있기 때문에 각 언어의 특성에 따라서 활용하는 것이 올바를 것이다.

<br>

> ##### 더 읽어보기
> 
> 위에서 언급한 숫자와 글자 사이의 연산에 대해서 잠깐 알아보도록 하자. 파이썬이 아닌 다른 자료형을 명시하는 언어에서 아래를 계산하면 재미있는 결과를 얻을 수 있다.
> 
> ```cpp
> /* 생략 */
> char var = 'a';
> cout << var + 1 << endl;
> /* 생략 */
> ```
> 
> 위에 있는 코드는 C++이라는 언어로 작성된 것이다. 생략된 줄을 제외하고 코드를 살펴보도록 하자. 현재 `var`라고 이름붙여진 자료를 저장할 수 있는 공간은 `char`이라는 자료형을 가지고 있다. 여기서 `char`은 `character`의 줄임말로 문자를 저장하는 자료형이다. 즉, 첫 번째 줄에서는 `var`라는 변수에다가 `a`라는 글자 하나를 저장한 셈이 된다. 두 번째 줄에서는 이렇게 저장된 값에 정수인 숫자 `1`을 더하고 있는 것이다. 이 코드의 결과는 무엇일까.
> 
> 결과는 정수 `98`이다. 여기서 중요한 점은 왜 `98`이라는 뜬금없는 결과가 나왔는가이며, 이것이 자료형을 사용하는 것과 어떻게 결부되느냐에 대한 것이다. 
> 
> 결론적으로는 컴퓨터가 `char`형을 저장할 때 각각의 글자를 미리 지정된 하나의 수로 저장하기 때문에 이러한 답이 나온 것이다. 이렇게 사용자가 입력한 문자 혹은 기호를 컴퓨터가 이해할 수 있는 신호로 변경하는 과정을 문자 인코딩(text encoding)이라고 한다. 대부분의 문자 인코딩은 ASCII라는 이름의 인코딩 방식을 기반으로 한다. 이 ASCII 방식의 인코딩에서 소문자 `a`는 `97`이라는 정수인 숫자에 대응되며, 이 `97`이라는 값에 `1`을 더했기 때문에 결과값이 `98`이 되는 것이다.
> 
> 우리가 이러한 사례에서 배울 수 있는 점은 이렇게 각 자료의 형태에 따라 저장되는 형태가 달라진다는 것(여기서는 문자가 ASCII 인코딩을 거쳐서 변수에 저장된다는 점)이며 이로 인하여 예상하지 못한 결과의 값이(여기서는 글자 `a`와 정수 `1`을 더한 값이 `98`이 되었다는 점) 나타날 수 있다는 점이다.

<br>

### 제2절 기본적인 자료형

아래에서는 기본적인 자료형에 대해서 학습해보도록 한다. 자료형은 대개 두 가지 형태로 나눌 수 있다. 하나의 값만을 저장할 수 있는 자료형을 스칼라(Scalar) 데이터 타입이라고 하며, 두 개 이상의 복합적인 값을 저장할 수 있는 자료형을 컴포지트(Composite) 데이터 타입이라고 한다.

#### 스칼라(Scalar) 데이터 타입


##### 숫자형(Number)

숫자형(Number)은 이름에서 알 수 있듯이 숫자인 형태로 만들어진 자료형이다. 이러한 숫자형 자료형은 흔히 정수(Integer)와 같은 형태만 존재한다고 알 수 있으나 이러한 숫자형에도 다양한 세부 형태가 존재한다.

###### 정수형(Integer)

정수형은 정수인 숫자 형태를 가지는 자료형이다. 이러한 정수형에는 양의 정수와 음의 정수, 그리고 0을 포함한다. 아래에서는 파이썬 코드 상에서 정수형의 자료의 자료형을 확인하는 과정이다. 

`type()`함수는 파이썬에서 변수의 자료형을 반환하는 함수이다. 아직 함수에 대해서 자세히 살펴보지는 않았지만, 입력 값에 대해서 정의된 기능을 수행하여 그 수행 결과 값을 반환하는 형태라고 이해 한 채 아래 코드를 살펴보도록하자.

```python
>>> var = 1
>>> type(var)
<class 'int'>
```

```python
>>> var = 0
>>> type(var)
<class 'int'>
```

```python
>>> var = -1
>>> type(var)
<class 'int'>
```

정수형 변수의 자료형은 예상하였듯이 `int(integer)`로 나타난다. 물론 혹자는 `int`를 감싸고 있는 `class`라는 단어에 집중할 수 있을 것이다. 우리는 일전에 `class`를 하나의 개념으로 받아들인다고 언급했었다. 즉, 컴퓨터가 이해할 수 있는 정수라는 개념을 사전에 정의하여 두었고, 해당하는 그 정수라는 클래스를 반환하였다고 보는 것이 합당할 것이다.

###### 실수형(Float)

파이썬에서 실수형(Floating Point)의 경우 소수점이 포함된 숫자를 의미하게 된다. 우리는 일전에 실수형이 어떻게 표현되는 지에 대해 언급한 적 있다. 

우리는 초등학교 등의 저학년 과정에서 소수점이 있는 계산을 할 때 소수점이 없는 형태로 먼저 계산을 한 뒤 자릿수에 따라서 소수점을 맞게 다시 찍는 과정을 통하여 연산을 진행하였다. 컴퓨터가 실수를 표현할 때는 이처럼 소수점을 고정하지 않고 그 위치를 나타내는 수를 별도로 표기하여 저장하는 부동소수점(浮動小數點, floating point) 방식으로 실수를 표현하게 된다. 여기서 부동은 고정되지 않고 물에 둥둥 떠서 부유(浮遊)하며 움직(動)이는 모습을 나타내는 단어이다.

아래의 코드를 통하여 실수형에 대해서 더 학습해보도록 하자.

```python
>>> var = 3.14
>>> type(var)
<class 'float'>
```

실수형 변수의 자료형은 예상하였듯이 `float`로 나타난다. 그렇다면 `3.0`이라는 수의 자료형은 어떻게 될까. 결과를 확인해보도록 하자.

```python
>>> var = 3.0
>>> type(var)
<class 'float'>
```

언뜻보기에 정수라고 생각할 수 있지만 수에 소수점이 포함된다면 그 수의 자료형은 실수형이 된다.

> ###### 더 읽어보기
> 
> 아주 작거나 아주 큰 실수의 경우에는 어떻게 표현되는 지에 대해서 확인해보자.
> 
> ```python
> >>> var = 0.0000000314
> >>> var
> 3.14e-08
> ```
> 
> 일반적으로 우리가 보는 실수와는 다른 모습의 결과 값이 나왔다. 이공계학을 공부하는 이들에게 이러한 표현방식은 친숙할 수 있다. 파이썬의 이러한 표기법을 지수 표기법(Exponential Notation)이라고 표현한다.
>
> 언급하였던 부동소수점의 방식에서는 소수점이 포함된 실수를 정수로된 유효숫자
> (Significant figures)와 정수로된 지수(Exponential)의 곱으로 나타낸다. 예를 들어
> `3.1415`라는 숫자는 `3.1415e+0`으로, `0.0000031415`의 경우에는 `3.1415e-06`라는 수
> 로 나타낼 수 있다.

##### None(NoneType)

만약 아무것도 없다는 것을 표현하기 위해서는  어떻게 해야할까. 파이썬에서 None은 아무런 값이 없다는 것을 나타낸다. 출력에서는 아무런 값이 나타나지 않게 된다.

```python
>>> var = None
>>> type(var)
<class 'NoneType'>
```

None의 자료형을 알아보기 위해 Type 함수를 이용한 결과 `NoneType`이 출력되는 것을 확인할 수 있다. 이러한 None은 이후에 조건에 따라 행위를 결정하는 조건문 등에서 아무것도 없음 혹은 비어 있음을 표현하는데 유용하게 사용될 수 있으며, 함수의 결과값이 존재하지 않음을 나타낼 때에도 사용되게 된다.

##### 논리형(Boolean)

논리형은 참과 거짓의 논리를 구분할 수 있도록 만들어진 자료형이며, `True`와 `False`로 이루어진다. 각각은 참과 거짓이라는 의미를 가진다. 아래 예시를 통하여 확인하여 보도록 하자.

```python
>>> a = True
>>> type(a)
<class 'bool'>
```

```python
>>> b = False
>>> type(b)
<class 'bool'>
```

이러한 논리형은 조건문에서의 조건을 구성할 때나 그 결과값으로 사용되기도 한다. 아래의 코드를 확인하여 보자.

```python
>>> 1 > 2
False
>>> 2 == 2
True
```

```python
>>> a = 1
>>> b = 2
>>> a == b
False
```

위와 같이 서로 다른 수 또는 변수를 비교할 때 참과 거짓의 결과를 논리형의 값으로 반환하고 있음을 확인할 수 있다. 여기서 참고할 점은 `같다`라는 의미를 표현할 때 대부분 `=`을 떠올리지만, 파이썬 및 다른 프로그래밍 언어에서는 대부분 `==`을 사용한다는 점이다.

#### 컴포지트(Composite) 데이터 타입

##### 문자열(String)

문자열(String)은 단어 혹은 문장과 같은 문자들의 집합체를 의미한다. 파이썬에서는 이를 나타내기 위하여 큰따옴표 혹은 작은따옴표로 감싸 표현하게 된다. 소수점을 포함한 숫자가 모두 실수 자료형을 가지게 되는 것과 같이 따옴표로 감싼 자료는 문자열로 취급된다. 아래의 코드를 확인하여 보자.

```python
>>> var = "a"
>>> type(var)
<class 'str'>

>>> var = '1'
>>> type(var)
<class 'str'>

>>> var = "3.14"
>>> type(var)
<class 'str'>
```

위 코드와 같이 숫자형의 자료를 따옴표로 감싸게 되어도 문자열 형태로 나타나게 됨을 주의하여야 한다.

그렇다면 이쯤에서 왜 문자형이 아닌 문자열이라고 표현하는 지에 대한 궁금증이 생길 수 있다. 일전에 우리는 컴포지트 데이터 타입을 두 개 이상의 복합적인 값을 저장할 수 있는 자료형이라고 이야기했다. 실질적으로 문자열은 글자들의 나열로 표현된다. 즉 하나의 글자 성분이 아닌 여러 개의 글자로 구성된다는 이야기이다. 

따라서 우리는 이러한 특성에 의하여 문자열이라고 흔히 표현하게 된다. 다만 특정 언어에서는 이러한 문자형 `char`과 문자열 `string 또는 char[] 등`을 구분하는 경우도 발생하니, 언어의 특성에 따라 이를 적절히 활용하도록 한다.

대부분의 인간의 커뮤니케이션이 문자로 이루어지기 때문에 문자열은 여러 기능을 탑재하고 있으며, 우리도 많은 지면을 할애하여 문자열에 대해서 설명하고자 한다.

<br>

###### 문자열을 만드는 법

문자열은 흔히 아래와 같은 방법으로 만들게 된다. 다만 문자열 안에 큰따옴표 혹은 작은따옴표를 포함하기 위해서는 전체를 둘러싸는 따옴표를 내부에 포함되는 따옴표와 다른 것을 택하여 사용하여야 한다. 아래의 코드를 살펴보도록 하자.

```python
>>> "Hello World"
'Hello World'

>>> 'Hello World'
'Hello World'

>>> """Hello World"""
'Hello World'

>>> '''Hello World'''
'Hello World'
```

기본적으로 문자열을 만들 때에는 따옴표를 한 개 혹은 세 개 사용하여 문자열을 만들 수 있다.

```python
>>> "Hello "World""
  File "<stdin>", line 1
    "Hello "World""
            ^^^^^
SyntaxError: invalid syntax

>>> 'Hello 'World''
  File "<stdin>", line 1
    'Hello 'World''
            ^^^^^
SyntaxError: invalid syntax
```

만약 내부에 따옴표를 삽입하고 싶다하여 동일한 따옴표를 사용하게 되면 올바르지 못한 문법(invalid syntax)이라는 오류를 만나게 된다. 이러한 경우를 피하기 위해서는 아래와 같이 사용하면 된다.

```python
>>> "Hello 'World'"
"Hello 'World'"

>>> 'Hello "World"'
'Hello "World"'

>>> "Hello \"World\""
'Hello "World"'

>>> 'Hello \'World\''
"Hello 'World'"
```

서로 다른 따옴표의 조합이나 `백슬래시(\)`를 이용하여 문자열 내부에 따옴표를 추가할 수 있다.

<br>

###### 이스케이프 시퀀스

이스케이스 시퀀스(Escape Sequence)란 프로그램 언어도 특정 문자를 명령을 위한 문자로 사용하고 있기 때문에 이러한 이유로 표현할 수 없는 문자들을 표현해주기 위해서 만들어졌다. 대게 `백슬래쉬(\)`와의 조합을 통하여 사용하며, 한글 윈도우를 사용하는 사용자라면 `한국 원 통화기호(₩)`가 대체되어 표기되기도 한다.

아래의 코드를 보며 이스케이프 시퀀스의 사용 예를 확인해보도록 하자.

```python
>>> print("Hello \nWorld")
Hello
World

>>> print("Hello \tWorld")
Hello 	World

>>> print("Hello \\World")
Hello \World
```

위에서 사용한 `print()`함수는 입력받은 값을 출력하는 함수이다. 결과값을 살펴보면 각각의 이스케이프 시퀀스가 여러 출력 결과를 나타낸 것을 볼 수 있으며, 위의 문자열을 만드는 법에서 큰따옴표 및 작은따옴표를 출력할 때 백슬래시를 사용한 것도 이스케이프 시퀀스의 일종이다. 

이스케이프 시퀀스의 몇 가지 종류로는 아래와 같다.

|  코드  | 표현                            |
|:------:|---------------------------------|
|   \n   | 줄 바꿈을 만들 때 사용           |
|   \t   | 문자열에서 탭 간격을 만들 때 사용|
|  \\'	  | 작은따옴표를 표현할 때 사용      |
|  \\"	  | 큰따옴표를 표현할 때 사용        |
| \\ \\  | 백슬래시를 표현할 때 사용        |

더 많은 이스케이프 시퀀스가 있으나 자주 사용하는 이 정도만 확인하고 넘어가도록 하자.

<br>

###### 문자열의 연산

파이썬에서는 문자열 간의 연산이 가능하다. 혹시라도 이전에 언급했던 문자와 숫자 간의 연산과는 확연하게 다르다. 기본적으로 이쪽은 문자가 아닌 문자열이기 때문이다. 

아래의 코드로 간단하게 짚고 넘어가도록 하자.

```python
>>> 'Hello' + 'World'
'HelloWorld'

>>> 'Hello' * 2
'HelloHello'
```

<br>

###### 인덱싱과 슬라이싱

대부분의 사람들은 숫자를 셀 때 1부터 시작하겠지만, 대부분의 컴퓨터 및 프로그래밍 언어는 0부터 숫자 세기를 시작한다. 우리는 어느 단어나 문자가 있을 때 특정 글자를 표현하기 위해서 앞에서부터 몇 번째 글자 등으로 표현하기도 한다. 파이썬에서도 문자열 중 어느 특정한 한 글자를 표현하는 방법이 있으며, 이를 문자열 인덱싱이라고 한다.

아래의 코드를 통하여 문자열 인덱싱에 대해서 알아보도록 하자.

```python
>>> var = "Hello"

>>> var[0]
'H'

>>> var[3]
'l'

>>> var[4]
'o'

>>> var[-1]
'o'

>>> var[-3]
'l'
```

인덱싱은 가장 첫번째 글자는 `0`으로 시작하여 문자열에서 해당하는 순서의 값을 추출하게 된다. 이때 뒤에서부터 계산하려면 음수의 값을 넣으면 되며, 가장 마지막 글자를 `-1`로 하여 계산하게 된다.

인덱싱과 슬라이싱에서 가장 중요한 점은 주어진 문자열에 대한 부분 문자열을 추출할 수 있다는 점이다. 쉽게 말하자면 몇 번째 글자부터 몇 번째 글자만을 떼어내어 사용할 수 있다는 점이다. 아래의 코드를 확인하여 보자.

```python
>>> var = "Hello Python World"
>>> var[6:12]
'Python'
```

파이썬에서는 대괄호 안에 특정 시작값과 콜론, 끝값을 구성하여 슬라이싱을 진행할 수 있다. 이 때 다음과 같은 규칙이 성립된다.

$$ var[start:end] $$ 일 때 추출의 범위는

$$ start \leq var < end $$

단, $$ var $$은 정수, $$ start $$의 값이 없을 때에는 문자열의 처음부터 슬라이싱을 시작하며, $$ end $$의 값이 없을 때에는 문자열의 끝까지 슬라이싱한다.

아래를 통해 슬라이싱의 몇 가지 예시를 확인하여 보도록 하자.

```python
>>> var = "Hello Python World"

>>> var[:10]
'Hello Pyth'

>>> var[10:]
'on World'

>>> var[:]
'Hello Python World'

>>> var[6:-6]
'Python'
```

인덱싱과 슬라이싱이 가능한 이유는 컴포지트 데이터 타입이며 반복 가능(iterable)하기 때문이다. 이를 통해 앞으로 소개할 반복 가능한 컴포지트 데이터 타입에서도 이러한 인덱싱과 슬라이싱 기법이 유효함을 추측해볼 수 있다. 

이때 반복 가능이라는 의미는 각 요소를 하나씩 차례대로 반환 가능하다는 의미로, 인덱싱과 슬라이싱은 이 개념을 이용하여 각각 반복 가능한 특정 요소의 위치의 따라 해당 요소를 참조하는 행위, 인덱스를 기반으로 반복 가능한 요소의 하위 요소 혹은 집합을 추출하는 것이라고 정의내릴 수도 있다.

<br>

###### 문자열 관련 함수

문자열은 사용자와의 측면에서 가장 많이 이용되는 자료형임이 분명하다. 따라서 이러한 문자열을 더욱 효율적으로 사용할 수 있도록 도와주는 함수들이 많이 구비되어 있는 경우가 많다. 본 지에서도 많이 이용하는 몇가지의 함수를 함께 살펴보도록 한다. 다만 아래에서 설명하는 함수보다 더 많은 유용한 함수가 존재하기 때문에 스스로 필요한 함수들을 학습하는 것도 좋은 방향이 될 것이다.

<br>

**문자열 포맷을 지정하기 위한 format 함수**

대부분의 프로그램에서는 변수와 값과 지정된 형식의 문구를 함께 사용하는 경우가 많다. 가령 소비재의 계산을 위한 프로그램을 작성한다고 가정했을 때 사용자에게 출력하는 문구가 `{금액}원을 결제합니다.` 등의 문구를 출력하여야 한다. 이때 `{금액}` 부분의 경우에는 변수 등에 저장되어 있는 값으로 출력 시마다 변경되어야 하는 값이다. 이러한 문제상황을 쉽게 해결하기 위해 `format()` 함수가 제시된다.

아래를 통하여 그 코드를 확인하여 보자.

```python
>>> print("{}원을 결제합니다.".format(10000))
10000원을 결제합니다.

>>> print("{}원을 결제합니다.".format(1000))
1000원을 결제합니다.

>>> print("{}원을 {}를 통하여 결제합니다.".format(1000, '카드'))
1000원을 카드를 통하여 결제합니다.

>>> print("{}원을 {}를 통하여 결제합니다.".format(1000, '현금'))
1000원을 현금를 통하여 결제합니다.

>>> print("{price}원을 {payment}를 통하여 결제합니다.".format(payment='카드', price="1000"))
1000원을 카드를 통하여 결제합니다.
```

각 중괄호에 별도의 이름을 지정하지 않으면 순서대로 입력하며되며, 이름을 지정했을 때에는 `이름=값` 형식으로 입력하면 된다.

<br>

**소문자와 대문자 간의 변환**

파이썬에서는 소문자와 대문자 간의 변환을 쉽게 할 수 있으며, 이 때 이용하는 것이 `upper()` 함수와 `lower()`함수이다.

```python
>>> print("Hello World".upper())
HELLO WORLD

>>> print("Hello World".lower())
hello world
```

<br>

**특정 문자열 변경하기**

문자열의 특정 단어를 모두 대치(replace)하고 싶을 때에는 `replace` 함수를 이용한다.

```python
>>> print("Hello World".replace('Hello', 'Good Morning'))
Good Morning World

>>> var = "Hello Hello World"
>>> var.replace("Hello", "Nice")
'Nice Nice World'
```

<br>

**문자열 분리하기**

띄어쓰기에 따라 분리된 문자열이나, 특정 구분 기호로 분리된 자료를 파이썬에서는 보다 쉬운 형태로 분리하여 낼 수 있다. 이 때 이용하는 함수가 `split()`이다. 아래의 코드를 통해 확인하여 보자.

```python
>>> var = "동해물과 백두산이 마르고 닳도록"
>>> print(var.split(' '))
['동해물과', '백두산이', '마르고', '닳도록']

>>> print("나보기가, 역겨워, 가실때에는".split(','))
['나보기가', ' 역겨워', ' 가실때에는']

>>> print("010-1234-5678".split('-'))
['010', '1234', '5678']

>>> print("2022-09-14".split('-'))
['2022', '09', '14']
```

여러 비정형화된 데이터를 이용할 때 `split()`함수는 유용하게 사용될 수 있다. 이때 확인할 점은 반환되는 값이 대괄호로 둘러싸여진 자료형이다. 이러한 자료형의 형태를 조회하기 위하여 `type()`함수를 사용하면 다음과 같다.

```python
>>> print(type([]))
<class 'list'>
```

대괄호로 둘러싸여 쉼표로 구분되는 이러한 자료형을 `list`라고하며, 연속적으로 나열된 값에 대한 자료형이다. 앞으로의 컴포지트 데이터 타입에서 다시 언급하도록 하겠다.

<br>

**문자열 조합하기**

위에서는 문자열을 리스트의 형태로 분리하였다. 이와 반대되는 `join()`함수를 각 요소가 함수에 어디에 위치하는지를 중심적으로 확인해보도록 하자.

```python
>>> date = ['2022', '09', '14']
>>> '-'.join(date)
'2022-09-14'

>>> print(" ".join(['동해물과', '백두산이', '마르고', '닳도록']))
동해물과 백두산이 마르고 닳도록
```

<br>

**문자열의 양 끝의 공백 혹은 특정 문자열 제거하기**

파이썬에서는 양 끝 혹은 각각의 문자열의 끝에 추가된 특정 문자열을 제거할 수 있으며, 이때 앞뒤로 삽입된 불필요한 공백을 제거할 수 있다. 이러한 기능을 제공하는 함수는 세 가지로 각각 오른쪽, 왼쪽, 양쪽으로 제거하는 `rstrip()`, `lstrip()`, `strip()` 함수이다.

각각의 함수에 전해진 값에 따라서 해당하는 문자열를 제거하며, 이때 아무런 문자열를 전달하지 않으면 공백문자(Whitespace)를 제거한다.

```python
>>> var = "    Hello World    "

>>> var.rstrip()
'    Hello World'

>>> var.lstrip()
'Hello World    '

>>> var.strip()
'Hello World'
```

특정 값을 지우고 싶다면 아래처럼 원하는 문자열을 제거할 수 있다.

```python
>>> var = "####Hello World####"

>>> var.rstrip('#')
'####Hello World'

>>> var.lstrip('#')
'Hello World####'

>>> var.strip('#')
'Hello World'
```

이 때 유념할 점은 중간에 포함된 문자열은 삭제하지 않는다는 점이다.

```python
>>> var = "####Hello####World####"
>>> var.strip('#')
'Hello####World'
```

#### 자료형의 변환

자료형의 형변환(Casting)에 대해서 알아보도록 하자. 형변환은 말 그대로 자료형을 임의적으로 혹은 자의적으로 변환시키는 것을 의미한다. 파이썬에서는 각 자료형의 이름으로 만들어진 함수를 통하여 쉽게 형변환을 이루어낼 수 있다. 아래의 예시를 확인하여 보자

##### 실수형으로의 변환

```python
>>> var = 1
>>> float(var)
1.0
```

정수형 변수를 실수형으로 변경하면 의도한 대로 실수의 값을 반환하게 된다.

##### 정수형으로의 변환

```python
>>> var = 3.14
>>> int(var)
3
```

실수형 변수를 정수형 변수로 변경하게 되면 더 작은 범위로 자료형이 변환되기 때문에 그보다 더 확장되어 있는 정보는 소멸하게 된다. 따라서 정수 `3`만이 남고 소수점 아래의 수는 버림처리 된다.

##### 논리형으로의 변환

```python
>>> var = 1
>>> bool(var)
True

>>> var = 0
>>> bool(var)
False

>>> var = 3
>>> bool(var)
True
```

논리형의 경우에는 그 양상이 다양하다. 먼저 정수형에서 논리형으로 값을 변화시키면 0이 아닌 값은 모두 `True`에 대응되며 오직 `0`만이 `False`에 대응된다.

```python
>>> var = 1.0
>>> bool(var)
True

>>> var = 0.0
>>> bool(var)
False

>>> var = 3.0
>>> bool(var)
True
```

실수형에서 논리형으로 변환하게 되어도 오직 `0.0`만이 `False`에 대응된다.

```python
>>> var = "Hello"
>>> bool(var)
True

>>> var = ""
>>> bool(var)
False
```

문자형의 경우에는 빈 문자열만이 `False`에 대응됨을 확인할 수 있다.

```python
>>> var = []
>>> bool(var)
False

>>> var = ()
>>> bool(var)
False

>>> var = {}
>>> bool(var)
False
```

리스트나 튜플, 딕셔너리 등의 컬렉션 타입의 경우에는 내부에 요소가 없는 빈 경우에만 `False`에 대응된다.