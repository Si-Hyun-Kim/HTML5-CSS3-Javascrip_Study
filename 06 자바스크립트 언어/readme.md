# 자바스크립트 시작
## 자바스크립트 언어란?
- `자바스크립트(Javascript)`는 1995년 `넷스케이브(Netscape Communications Corporation)`사에서 개발되고 `Netscape Navigator 2.0` 브라우저에 최초로 탑재되어 웹 프로그래밍의 개념을 창시한 언어이다.
- 자바스크립트 언어의 특징
  - 자바스크립트는 조각난 소스 코드 형태로 HTML 페이지에 내장된다.
  - 자바스크립트 소스 코드는 컴파일 과정 없이 브라우저 내부의 자바스크립트 처리기(인터프리터)에 의해 바로 실행된다.
  - 자바스크립트는 C언어 구조를 차용하고 단순화시켜 쉽게 배울 수 있다.

> **자바스크립트와 자바는 다른 언어**<br>
> 자바(Java)가 자바스크립트(Javascript)를 줄여 말하는 것으로 오해하는 사람들이 있다. 이 둘은 서로 다른 언어이다. 자바는 완벽한 객체 지향 기능을 갖추고 PC, 모바일, 웹 서버 등 다양한 환경에서 소프트웨어를 개발하는데 사용되는 범용 언어이지만, 자바스크립트는 웹 페이지에 내장되어 브라우저에서 실행되거나 웹 서버에서 실행되는 응용프로그램을 작성하는데 사용된다. 자바 언어도 웹 서버 프로그램 개발에 많이 사용되는데 이를 자바 서블릿(servlet)이라고 부른다. 한편 JSP(Jave Server Page)는 웹 서버 상에서 실행되는 또 다른 스크립트 언어이다. JSP 프로그램은 실행 전에 자바 클래스 (서블릿)으로 변환되어 실행된다.

## 웹 페이지에서 자바스크립트의 역할
- 사용자의 입력 및 계산
- 웹 페이지 내용 및 모양의 동적 제어
- 브라우저 제어
- 웹 서버와의 통신
- 웹 애플리케이션 작성

# 자바스크립트 코드의 위치
- HTML 태그의 이벤트 리스너 속성에 작성 [[html 태그의 이벤트 리스너 속성에 자바스크립트 코드 작성]](Code/ex_06-01.html)
- `<script></script>` 내에 작성 [[`<script>` 태그에 자바스크립트 코드 작성]](Code/ex_06-02.html)
- 자바스크립트 파일에 작성 [[자바스크립트 파일 작성 및 불러오기]](Code/ex_06-03.html)

```html
<script src="파일이름.js">
  // HTML5부터 이곳에 자바스크립트 코드를 추가 작성하면 안 됨
</script>
```

- URL 부분에 작성 [[링크의 href에 자바스크립트 코드 작성]](Code/ex_06-04.html)

> **이벤트와 이벤트 리스너**<br>
> - `이벤트(event)` 사용자의 입력 행위를 브라우저가 웹 페이지에 전달하는 수단.
> - `이벤트 리스너(event listener)` 이벤트를 처리하는 자바스크립트 코드
> - onclick, onchange, onmousemove 와 같이 이벤트 앞에 on을 붙인 이름이 HTMl 태그의 리스너 속성으로 사용되며, 이 속성에 자바스크립트 코드를 작성한다.

<hr>

## 자바스크립트로 HTML 콘텐츠 출력 [[document.write()로 웹 페이지에 HTML 콘텐츠 출력]](Code/ex_06-05.html)
- 자바스크립트 코드로 HTML 콘텐츠를 웹 페이지에 직접 삽입하여 바로 브라우저 윈도우에 출력되게 할 수 있다.
- `document.write()`, `document.writeln()` 을 사용하면 된다.

예)
```javascript
document.write("<h3>Welcome!</h3>1");
```
> 이 코드가 실행되면 웹 페이지 내 코드가 실행되는 위치에 "Welcome!" 텍스트가 출력된다. `writeln()`과 `write()`의 사용법은 동일하며 `writeln()`은 텍스트에 `\n`을 덧붙여 출력한다. `\n`은 다음 줄로 넘어가는 것이 아닌 빈 칸 하나이다. 다음 줄로 넘어가고싶다면 `<br>` 태그를 출력하면 된다.

<hr>

## 자바스크립트 다이얼로그 : 사용자 입력 및 메시지 출력
### 프롬프트 다이얼로그, prompt("메시지", "디폴트 입력값")
- `prompt()` 다이얼로그를 출력하고 사용자로부터 문자열을 입력받아 리턴한다.
- 디폴트 입력값은 생략 가능하다.
- 일반적으로 사용자가 입력한 문자열을 리턴하지만, 아무 값도 입력되지 않았으면 `""`를, 취소 버튼이나 강제로 다이얼로그를 닫은 경우 `null`이 리턴된다.

```javascript
let ret = prompt("이름을 입력하세요", "홍길동");
if(ret ==  null) {
  // 취소 버튼이나 다이얼로그를 닫은 경우
}
else if(ret == "") {
  // 문자열 입력 없이 확인 버튼 누른 경우
}
else {
  // ret에는 사용자가 입력한 문자열
}
```

### 확인 다이얼로그, confirm("메시지")
- `confirm()` `메시지`와 `확인/취소(OK/CANCLE) 버튼`을 가진 다이얼로그 출력
- 사용자가 확인 버튼을 누르면 `true`를, 취소 버튼이나 강제로 다이얼로그를 닫으면 `false`를 리턴한다.

```javascript
let ret = confirm("전송할까요");
if(ret == true) {
  // 사용자가 "확인" 버튼을 누른 경우
}
else {
  // 취소 버튼이나 다이얼로그를 닫은 경우
}
```

### 경고 다이얼로그, alert("메시지")
- `alert()` 함수는 다이얼로그를 출력하여 단순히 메시지를 전달한다.

```javascript
alert("클릭하였습니다.");
```

<br><hr>

# 데이터 타입과 변수
## 자바스크립트 식별자
- `식별자(identifier)` 자바스크립트 개발자가 자바스크립트 프로그램의 변수, 상수(리터럴), 함수에 붙이는 이름
- 식별자 규칙
  - 첫 번째 문자 - 알파벳(A-Z, a-z), 언더스코어(_), $ 문자만 사용 가능
  - 두 번째 이상 문자 - 알파벳, 언더스코어(_), 0-9, $ 사용 가능
  - 대소문자 구분 - myHome과 myhome은 다른 변수

> **가독성 높은 식별자 만들기**<br>
> 식별자는 의미를 담을 수 있도록 최대한 길게 쓰는 것이 좋다. 예를 들면 다음과 같다.<br>
> `appCodeName, previousElementSibling, dedicateWorkerGlobalScope`
> <br><br>
> 또한, 두 단어로 구성되는 식별자를 만들 때, 가독성을 높이기 위해 단어의 첫 글자는 대문자로 하는 이른바 헝가리언 이름 규칙이 바람직하다. 다음은 헝가리언 이름 사례이다.<br>
> `numberOfStudent, studentID, parseInt()`

<hr>

## 문장 구분
- 자바스크립트 프로그램의 기본 단위는 문장(statement)이며, 세미콜론(;)으로 문장과 문장을 구분한다.
- 한 줄에 한 문장만 있는 경우 세미콜론을 생략할 수 있다.

<hr>

## 주석문
- 설명이나 메모 목적으로 삽입한 텍스트
- 프로그램 코드로 처리되지 않는다.
- `//` 한 라인 주석문
- `/* */` 여러 라인 주석문

<hr>

## 데이터 타입
### 데이터 타입 종류
- `숫자 타입` 42, 3, 14, ...
- `논리 타입` true, false
- `문자열 타입` '좋은 세상', "a", "365", "2+4", ...
- `객체 레퍼런스 타입` 객체를 가리킴. C 언어의 포인터와 유사
- `null` 값이 없음을 표시하는 특수 키워드. Null, NULL과는 다름

<hr>

## 변수
- 자바스크립트 프로그램이 실행 중에 데이터를 저장하는 공간
- 이름을 붙여 사용한다.
- 스크립트 언어로서 변수에 데이터 타입을 지정하지 않는다.

### 변수 선언 방법
- `var` 를 이용하는 방법
- `let` 을 이용하는 방법
- `const` 를 이용하는 방법

> `var` 또는 `let` 지정 없이 변수를 선언할 수 있는데, 이 때는 `var` 타입으로 자동으로 지정된다.

### 변수 타입과 값
- 자바스크립트에는 변수 타입이 없으므로 `var`|`let`|`const` 와 변수명만으로 선언한다.

### 변수의 사용 범위와 생명 [[지역 변수와 전역 변수, 블록 변수]](Code/ex_06-06.html)
변수는 사용 범위에 따라 다음 3가지로 나뉜다.
- `전역 변수` 함수 밖에서 선언되거나 `var`|`let` 키워드 없이 아무 곳에서나 선언된 변수. 프로그램이 실행을 시작할 때 생겨나서 프로그램 종료 시까지 생존. 프로그램 전역에 걸쳐 사용 가능
- `지역 변수` 함수 내에서 `var`|`let` 키워드로 선언된 변수. 함수가 시작되면 생겨나서 함수가 종료되면 사라지므로 선언된 함수 내에서만 사용 가능
- `블록 변수` `let` 키워드로 `if`,` while`, `for` 등 블록 내에서 선언된 변수. 블록 내에서만 사용. 블록이 끝나면 사라지므로 블록 바깥에서는 접근 불가.

> 2015년 전에는 `전역 변수`와 `지역 변수`밖에 없었으나 2015년 ECMAScript(ES6) 표준에서 블록 범위가 새로 추가되고 블록 범위를 선언하는 `let` 이 추가되었다.

```javascript
let = x;    // 전역 변수 x 선언. var로 선언해도 동일
function f() {
  let y;    // 함수 f() 내에서만 사용되는 지역 변수 y 선언. var로 선언해도 동일
  x = 10;   // 전역 변수 x에 10 저장
  y = 20;   // 지역 변수 y에 20 저장
  z = 30;   // 새로운 전역 변수 z가 선언되고 30이 저장됨
  if(y == 20) {
    let b = 40;   // if 블록에서만 사용되는 블록 변수 b 선언
    b++
  }
  // 이곳에서는 블록 변수 b에 접근할 수 없음
  // 이곳에서는 변수 x, y, z에 모두 접근 가능
}
// 여기서는 변수 x와 z만 접근 가능. 지역 변수 y와 블록 변수 b는 접근 불가
```

### this로 전역 변수 접근
- 지역 변수와 전역 변수의 이름이 같을 때, this를 이용하면 함수 내에서도 전역 변수를 접근할 수 있다.
- 다음은 x라는 같은 이름의 지역 변수와 전역 변수가 있는 경우이다.
- 함수 f() 내에서 변수 x를 접근하면 지역 변수 x이며, this.x로 하면 전역 변수에 접근할 수 있다.

```javascript
var x = 10;   // 전역 변수 x 선언
function f() {
  var x;   // 지역 변수 x 선언
  x = 1;   // 지역 변수 x에 1 저장
  this.x = 100;   // 전역 변수 x에 100 저장
}
```

> `let`으로 선언된 전역 변수는 this로 접근할 수 없다.

<hr>

## let의 특징
- var는 동일한 변수를 재선언할 수 있지만, let으로는 동일한 변수를 재선언할 수 없다.
- let은 변수의 사용 범위를 블록 내로 제한한다.

> `let`은 `var`를 사용할 때 발생하는 개발자들의 코딩 오류를 줄이기 위해 2015년 ES6 표준에 새로 도입되었음

### let은 동일한 변수를 재선언할 수 없다
```javascript
var x = 1;
var x = 2; // 오류가 발생하지 않는다.
```
```javascript
let x = 1;
let x = 2; // 오류 발생. 재선언 불가
```

### let은 변수 사용 범위를 블록 내로 제한
``` javascript
if(a == b) {
  let x = 10;  // x는 if 블록에서만 사용
}
x++; // 오류 발생. x 사용 불가
```
```javascript
for(let n=0; n<10; n++) {  // n과 x는 for 블록에서만 사용
  let x = 10;
}
x++; // 오류 발생. x 사용 불가
n++; // 오류 발생. n 사용 불가
```

### var보다 let 사용 권고
- 동일한 변수를 var로 재선언하는 실수를 할 수 있기 때문에, var보다 let의 사용을 권한다.
- var를 사용한다하더라도 주의해서 사용하면 별 문제는 없다.

<hr>

## 상수
- 변하지 않는 값을 가지는 이름
- `const` 키워드를 이용하여 초기값과 함께 선언한다.
- 상수는 선언된 후 값을 변경할 수 없다.
- 또한 이미 선언된 상수를 재선언할 수 없다.
- const로 선언된 상수는 let과 마찬가지로 선언된 블록 범위 내에서만 사용된다.

<hr>

## 리터럴 [[리터럴]](Code/ex_06-07.html)
- 변수가 데이터 저장 공간의 이름이라면, 리터럴(literal)은 데이터 값 그 자체이다.

**자바스크립트 리터럴의 종류와 예**
<table>
  <thead>
    <tr>
      <td colspan="2">종류</td>
      <td>특징</td>
      <td>예</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="3">정수</td>
      <td>8진수</td>
      <td></td>
      <td>let n = 0o15;  // 8진수 15</td>
    </tr>
    <tr>
      <td>10진수</td>
      <td></td>
      <td>let n = 15;  // 10진수 15</td>
    </tr>
    <tr>
      <td>16진수</td>
      <td></td>
      <td>let n = 0x15;  // 16진수 15</td>
    </tr>
    <tr>
      <td rowspan="2">실수</td>
      <td>소수형</td>
      <td></td>
      <td>let heigth = 0.1234;</td>
    </tr>
    <tr>
      <td>지수형</td>
      <td></td>
      <td>let heigth = 1234E-4;</td>
    </tr>
    <tr>
      <td rowspan="2">논리</td>
      <td>참</td>
      <td>true</td>
      <td>let condition = true;</td>
    </tr>
    <tr>
      <td>거짓</td>
      <td>false</td>
      <td>let condition = false;</td>
    </tr>
    <tr>
      <td colspan="2" rowspan="2">문자열</td>
      <td>""로 묶음</td>
      <td>let hello = "안녕하세요";</td>
    </tr>
    <tr>
      <td>''로 묶음</td>
      <td>let hello = 'kitae';</td>
    </tr>
    <tr>
      <td rowspan="2">기타</td>
      <td>null</td>
      <td>값이 없음을 뜻함</td>
      <td>let ret = null;</td>
    </tr>
    <tr>
      <td>NaN</td>
      <td>수가 아님을 뜻함</td>
      <td>let n = parseInt("abc");  // 이때 parseInt()는 NaN을 리턴;</td>
    </tr>
  </tbody>
</table>

### 문자열 내 문자열
- 이중인용부호("")로 만든 문자열 안에 다른 문자열을 포함하고자 하면 단일인용부호('')를 사용하며, 그 반대도 가능하다.

<br><hr>

# 식과 연산자
- 식(expression)을 계산하여 결과를 얻는 과정을 연산이라고 한다.

**자바스크립트의 연산과 연산자 종류**
|연산|연산자|
|:-:|-----|
|산술| + - * / % |
|증감| ++ -- |
|비트| & \| ^ ~ |
|시프트| >> << >>> |
|대입| = *= /= -= += &= ^= \|= <<= >>= >>>= |
|비교| > < >= <= == != |
|논리| && \|\| ! |
|조건| ? : |

<hr>

## 산술 연산 [[산술 연산]](Code/ex_06-08.html)
- `산술 연산자`는 더하기(+), 빼기(-), 곱하기(*), 나누기(/), 나머지(%)의 5가지이다.
- `나누기(/)의 결과는 실수`이다. 따라서 32/10의 결과는 3이 아닌 3.2이다.
- 나머지(정수 값) 값은 % 연산자로 구한다.

<hr>

## 증감 연산
- 증감 연산자는 `++`, `--`의 두 가지이며, 변수의 앞 또는 뒤에 붙어 값을 1 증가시키거나 1 감소시킨다.

```javascript
let a=1;
a++;    // a 값 1 증가. a는 2가 됨
++a;    // a 값 1 증가. a는 3이 됨
```

- 연산자가 변수의 앞에 붙을 때 `전위 연산자`라 부르고, 뒤에 붙을 때 `후위 연산자`라고 부른다.
- 모두 1 증가시키는 연산을 실행하지만 연산 결곽로 반환하는 값은 서로 다르다.

<br>

**증감 연산자**
|연산자|내용|
|:----:|----|
| a++  | a를 1 증가하고 증가 전의 값 반환 |
| ++a  | a를 1 증가하고 증가된 값 반환 |
| a--  | a를 1 감소하고 감소 전의 값 반환 |
| --a  | a를 1 감소하고 감소된 값 반환 |

<hr>

## 대입 연산 [[대입 연산]](Code/ex_06-09.html)
```javascript
let a=1, b=3;
a = b;        // a에 b 값을 대입하여 a=3, b=3이 된다.
a += b;       // a = a + b의 연산이 이루어져, a=6, b=3이 된다.
```
<br>

**대입 연산자**
|연산자|내용|
|:----:|:--:|
|a = b|b 값을 a에 대입|
|a += b|a = a + b와 동일|
|a -= b|a = a - b와 동일|
|a *= b|a = a * b와 동일|
|a /= b|a = a / b와 동일|
|a %= b|a = a % b와 동일|
|a &= b|a = a & b와 동일|
|a ^= b|a = a ^ b와 동일|
|a \|= b|a = a \| b와 동일|
|a <<= b|a = a << b와 동일|
|a >>= b|a = a >> b와 동일|
|a >>>= b|a = a >>> b와 동일|

<br>

> **증감 연산자가 대입 연산자의 속도가 빠르다.**<br>
> `a+=b;`가 `a=a+b;`보다 연산 속도가 빠르다. 임의의 두 값을 더해 임의의 변수에 저장하는 일반적인 처리 과정보다, 자기 자신에게 더하는 연산의 처리 과정이 단순하기 때문이다. 값은 이유로 `a++;`이 `a=a+1;`보다 연산속도가 빠르다.

<hr>

## 비교 연산 [[비교 연산]](Code/ex_06-10.html)
- 두 값을 비교하고 결과가 `true`나 `false`인 연산

```javascript
let age = 25;
let res = (age > 20);   // res는 true
```
<br>

**비교 연산**
|연산자|내용|
|:----:|----|
|a < b | a가 b보다 작으면 true|
|a > b | a가 b보다 크면 true|
|a <= b | a가 b보다 작거나 같으면 true|
|a >= b | a가 b보다 크거나 같으면 true|
|a == b | a가 b와 같으면 true|
|a != b | a가 b와 같지 않으면 true|

<hr>

## 논리 연산 [[논리 연산]](Code/ex_06-11.html)
- 자바스크립트의 논리 연산은 `AND`, `OR`, `NOT`의 3가지이다.
```javascript
let score = 90;
let age = 20;
let res = ((score > 80) && (age < 25>));  // res=true
```
<br>

**논리 연산자(표에서 a, b는 true나 false)**
|연산자|별칭|내용|
|:----:|:--:|----|
|a && b|논리 AND 연산|a, b 모두 true 일 때 true 리턴|
|a \|\| b|논리 OR 연산|a, b 중 하나라도 true이면 true 리턴|
|  !a  |논리 NOT 연산|a가 true이면 false 값을, false이면 true 값 리턴|

<hr>

## 조건 연산 [[조건 연산]](Code/ex_06-12.html)
- 조건식 condition과 2개의 식 expT, expF로 구성된다.
- condition이 true이면 조건식의 전체 결과는 expT의 계산 값이 되고, false이면 expF의 계산 값이 된다.
```
condition ? expY : expF
```
<hr>

## 비트 연산 [[비트 연산]](Code/ex_06-13.html)
- 비트끼리 `AND`, `OR`, `XOR`, `NOT`을 하는 비트 논리 연산과, 비트를 자리 이동시키는 `비트 시프트 연산`으로 나뉜다.

### 비트 개념
- 2진수의 한 자리수를 `비트(bit)`라 부르며, 8개의 비트를 `바이트(byte)`라고 한다.
- 10진수 10을 1바이트로 표현하면 00001010이다.

### 비트 논리 연산
|연산자|별칭|연산 설명|
|:----:|:--:|---------|
|a & b |비트 AND 연산|두 비트 모두 1이면 1, 그렇지 않으면 0|
|a \| b|비트 OR 연산|두 비트 모두 0이면 0, 그렇지 않으면 1|
|a ^ b |비트 XOR 연산|두 비트가 다르면 1, 같으면 0|
|  ~a  |비트 NOT 연산| 1을 0으로, 0을 1로 변환|

### 비트 시프트 연산
- 새로운 비트를 끝에 삽입하면서 비트의 자리를 이동하는 연산
- 비트들은 오른쪽이나 왼쪽으로 이동 가능하다.
- 저장 공간의 크기가 정해져 있으므로 새로 삽입되는 비트 때문에 끝에 있는 비트는 사라지게 된다.

**시프트 연산자**
|연산자|별칭|설명|
|:----:|:--:|----|
|a << b|산술적 왼쪽 시프트|a의 비트들을 왼쪽으로 b번 이동. 최하위 비트의 빈자리는 0으로 채움. 한 비트 시프트마다 곱하기 2의 효과 발생. a 값은 변화 없음|
|a >> b|산술적 오른쪽 시프트|a의 비트들을 오른쪽으로 b번 이동. 최상위 비트의 빈자리는 시프트 전 최상위 비트로 채움. 한 비트 시프트마다 나누기 2의 효과 발생. a 값은 변화 없음|
|a >>> b|논리적 오른쪽 시프트|a의 비트들을 오른쪽으로  b번 이동. 최상위 비트의 빈자리는 0으로 채움. a 값은 변화 없음|

<hr>

## 문자열 연산 [[문자열 연산]](Code/ex_06-14.html)
### 문자열 연결
- +, += 연산자는 문자열 연결에도 사용된다.
- 이때 피연산자 중 하나는 반드시 문자열이어야 한다.
- + 연산은 숫자 더하기와 문자열 연결 모두에 동시에 사용되므로 순서를 유의해야 한다.
- + 연산은 순서대로 이루어진다. 그러므로 숫자 더하기가 먼저 나오면 숫자를 합한 후 문자열과 연결하지만, 문자열이 먼저 나오면 문자열 연결이 먼저 처리된다.

### 문자열 비교
- 비교 연산자(!=, ==, >, <, <=, >=)는 문자열 비교에 그대로 사용되며, 사전에서 뒤에 나오는 문자열이 크다고 판단한다.

<br><hr>

# 조건문
- 조건을 검사하여 참인지 거짓인지에 따라 서로 다른 작업(프로그램 코드)을 실행하는 자바스크립트 문장

## if문 [[if-else 사용]](Code/ex_06-15.html)
- if문만으로 조건문을 만들 수 있음
- if의 조건식이 참이면 실행문을 실행한 후 if문을 벗어나며, 거짓이면 바로 if문을 벗어난다.
```javascript
if(조건식) {
  ... 실행문 ...  // 조건식이 참인 경우
}
```

## if-else문
- if-else문을 이용하면 조건식이 참인 경우와 거짓인 경우에 다른 코드를 실행할 수 있다.
```javascript
if(조건식) {
  ... 실행문1 ...  // 조건식이 참인 경우
}
else {
  ... 실행문2 ... // 조건식이 거짓인 경우
}
```

## 다중 if-else 문
if-else를 연속 작성하여 각 조건에 맞는 코드를 실행할 수 있다.
```javascript
if(조건식1) {
  실행문1   // 조건식1이 참인 경우
}
else if(조건식2) {
  실행문2   // 조건식2가 참인 경우
}
......
else {
  실행문n;  // 앞의 모든 조건이 거짓인 경우
}
```

<hr>

## switch문 [[switch문 사용]](Code/ex_06-16.html)
- 값에 따라 서로 다른 코드를 실행할 때, `if-else문`보다 `switch문`이 적합하다.
- switch(식)는 괄호 안에 있는 '식'의 결과가 case 문의 '값'과 일치하는 실행 문장으로 분기한다.
- 실행 문장들을 실행한 후 break 문을 만나면 switch 문을 벗어난다.
- 일치하는 case 문이 없으면 `default 문`으로 바로 분기한다.
- default문은 생략 가능하다.
```javascript
switch(식) {
  case 값1:    // 식의 결과가 값1과 같을 때
    실행 문장 1;
    break;
  case 값2:    // 식의 결과가 값2와 같을 때
    실행 문장 2;
    break;
  ...
  case 값m:    // 식의 결과가 값m과 같을 때
    실행 문장 m;
    break;
  default:    // 어느 값과도 같지 않을 때
    실행 문장 n;
}
```

### case 문의 값
- case 문의 값은 const로 선언된 상수나 리터럴만 가능하다.
- 하지만 case 문의 값에 변수나 식은 사용할 수 없다.

### switch문에서 break문의 역할
- case문 내의 실행 문장을 실행한 후 break 문을 만나지 못하면 break 문을 만날 때 까지 그 아래 다른 case의 실행 문장들을 계속 실행하여 내려간다.


<br><hr>

# 반복문
## for 문 [[for 문을 이용하여 10px~35px까지 텍스트 출력]](Code/ex_06-17.html)
- for 문은 반복 횟수를 아는 경우 주로 사용한다.
- for 문은 조건식이 true인 동안 작업문을 반복하여 실행한다.
- 초기문은 처음 한 번만 실행된다.
- 조건식에는 논리 연산이나 true/false 값 혹은 논리 값을 가진 변수를 사용할 수 있다.
- 조건식의 결과가 false이면 for 문을 벗어나 아래로 내려간다.
- 작업문이 하나의 문장으로 된 경우 중괄호는 생략 가능하다.

```javascript
for(초기문; 조건식; 반복 후 작업) {
  ... 작업문 ...
}
```
<hr>

## while 문 [[while 문으로 0~n까지의 합 구하기]](Code/ex_06-18.html)
- while 문 역시 조건식이 참인 동안 작업문을 반복 실행한다.
- while 문은 반복 회수를 알 수 없는 경우 주로 이용한다.

```javascript
while(조건식) {
  ... 작업문 ...
}
```

> **parseInt() 함수**<br>
> parseInt(문자열) 함수는 문자열을 숫자로 바꾸어 리턴하는 자바스크립트 함수로서, parseInt("25")는 숫자 25를 리턴한다.

<hr>

## do-while 문 [do-while 문으로 0에서 n까지의 합 구하기](Code/ex_06-19.html)
- 작업문은 최소 한 번 실행되며, 조건식을 검사하여 true인 동안 작업문이 반복 실행된다.
```javascript
do {
  ... 작업문 ...
} while(조건식);
```

<br>

## break 문 [break 문](Code/ex_06-20.html)
- break 문은 반복문을 벗어난다.
- 여러 반복문으로 중첩된 경우 현재 반복문 하나만 벗어난다.

```javascript
break;
```

<hr>

## continue 문 [[continue 문]](Code/ex_06-21.html)
- continue 문은 다음 반복으로 넘어가고자 할 때 사용된다.

```javascript
continue;
```

<br><hr>

# 함수
- 함수는 데이터를 전달받아 처리한 후 결과를 돌려주는(리턴하는) 코드 블록이다.

## 함수 개념
- 자바스크립트에서 데이터를 전달받아 정해진 작업을 수행하고 그 결과를 돌려(리턴)주도록 작성된 코드 블록
- 함수는 전달받는 데이터 없이 정해진 작업을 하기도 하고, 결과를 돌려주지 않기도 한다.

## 함수의 구성
```javascript
function 함수_이름(arg1, arg2, ..., argn) {
  ... 프로그램 코드 ...
  결과를 반환(리턴)하는 return 문
}
```

- `function` 함수 선언을 표시하는 키워드
- `함수_이름` 개발자가 정하는 것으로 함수의 목적에 맞게 이름 붙임
- `arg1, arg2, ... argn` 함수를 호출하는 곳으로부터 값을 받는 매개 변수. 여러 개 있을 때 콤마(,)로 분리. 값을 받지 않는 경우 매개변수 필요 없음
- `프로그램 코드` 함수의 작업을 실행하는 자바스크립트 코드
- `return 문` 함수의 실행을 종료하고 호출한 곳으로 되돌아 가면서 함수의 실행 결과를 반환하는 문

## 함수 호출(function call) [[adder() 함수 작성 및 호출]](Code/ex_06-22.html)
- 함수에게 일을 지시하고 받는 것
- 함수 호출에는 2가지 방법이 있다.
  - 변수 이름 = 함수 이름(arg1, arg2, ..., argN);   // 함수 호출 후 리턴 값 받음
  - 함수 이름(arg1, arg2, ..., argN);               // 함수 호출 후 리턴 값 받지 않음
- 함수가 아무 값도 리턴하지 않거나, 리턴한다고 해도 리턴 받는 값이 필요 없으면 두 번째 경우처럼 함수만 호출하면 된다.

<hr>

## 자바스크립트의 전역 함수 [[eval(), parseInt(), isNaN()]](Code/ex_06-23.html), [[구구단 출력 함수 만들기]](Code/ex_06-24.html)
### `eval()` 함수
- 수식이나 자바스크립트 문장을 문자열 형태로 전달받아 실행한 후 결과를 리턴한다.

예)
```javascript
let res = eval("2*3+*6");   // res는 30
```

### `parseInt()` 함수
- 문자열을 숫자로 변환하여 리턴한다.

예)
```javascript
let l = parseInt("32");       // "32"를 10진수로 변환하여, 정수 32 리턴
let m = parseInt("32", 16);   // "32"를 16진수로 해석하여, 정수 50 리턴
let n = parseInt("0x32");     // "0x32"를 자동으로 16진수로 해석하여, 정수 50 리턴
```

### isNaN() 함수와 parseInt() 함수
- false가 거짓 값을 나타내는 리터럴 키워드인 것과 같이 NaN은 숫자가 아님을 나타내는 리터럴 키워드이다.
- isNaN()은 매개 변수의 값이 NaN인지 비교하여 맞으면 true를 리턴하는 자바스크립트 함수이다.

```javascript
let n = NaN;
let b = isNaN(n);  // true 리턴
```

```javascript
let n = parseInt("hello");
if(isNaN(n))
  document.write(n + "는 숫자가 아닙니다.");
```

**자바스크립트에서 제공하는 전역 함수**
|전역 함수명|설명|
|:---------:|----|
|eval(exp)|exp의 자바스크립트 식을 계산하고 결과 리턴|
|parseInt(str)|str 문자열을 10진 정수로 변환하여 리턴|
|parseInt(str, radix)|str 문자열을 radix 진수로 해석하고, 10진 정수로 바꾸어 리턴|
|parseFloat(str)|str 문자열을 실수로 바꾸어 리턴|
|isFinite(value)|value가 숫자이면 true 리턴|
|isNaN(value)|value가 숫자가 아니면 true 리턴|

> `NaN`은 Not a Number를 줄여 만든 단어이다. false, true, null처럼 NaN은 숫자가 아님을 나타내는 상수이다.

> `eval()` 함수는 여러가지 위험성을 내포하고 있어 사용을 권하지 않는다. 하지만 문자열로 구성된 산술식을 쉽게 계산할 수 있기 때문에 여전히 사용된다. eval()을 사용하지 않으려면 무료나 상용으로 배포되는 산술 계산 자바스크립트 패키지를 사용할 것을 권한다.