# 웹 개요

## 웹의 기본 목적과 구성
- 웹의 기본 목적
  - 한 컴퓨터에서 만든 문서(Document) 즉, `웹 문서`를 다른 컴퓨터에서 쉽게 볼 수 있도록 하는 것

- `World Wide Web(www)`
  - 웹 문서를 쉽게 주고 받을 수 있도록 시스템을 만든 것
  - 간단히 줄여 `web`이라고 부름

- 컴퓨터의 기능
  - Server
    - 문서나 이미지, 비디오 등의 데이터 저장
  
  - Client
    - 웹 서버로부터 데이터를 다운받아 사용자에게 보여주거나 사용자 데이터를 웹 서버에 업로드하는 사용자 인터페이스의 역할을 한다.


## 인터넷과 웹은 다르다
> 웹 != 인터넷

- `인터넷(Internet)`: 통신의 기본 체계로 웹이 나오기 훨씬 이전부터 존재

- `웹(World Wide Web)`
  - 여러 인터넷 `서비스` 중 하나
  - 문서를 서버 컴퓨터에 올려놓고 인터넷을 통해 클라이언트 컴퓨터에서 읽거나 쉽게 주고받을 수 있도록 만든 서비스


## 웹 브라우저
`웹 브라우저`
웹 서버에 접속해서 웹 페이지, 이미지, 동영상, 음악 등 다양한 데이터를 다운받아 보여주는 소프트웨어
예) Microsoft Edge, Chrome, Firefox, Opera 등

### 웹 브라우저 역사
- World Wide Web → Nexus
- Mosaic → Netscape Navigator → Netscape Communicator → Mozilla Firefox
- Internet Explorer → Microsoft Edge
- Opera
- Safari
- Chrome

#### 최초의 웹 브라우저, World Wide Web
`www`의 개념을 창시한 `팀 버너스리(Tim Berners-Lee)`가 최초로 만든 웹 브라우저


## 웹 서버와 웹 사이트
### 웹 사이트 구축
- 웹 서버로 사용할 컴퓨터에 웹 서버 소프트웨어를 설치하고, 작성한 웹 페이지들을 저장하고, 동영상, 이미지 등의 파일과 데이터베이스를 설치하는 것을 말함
- 또한, 사용자에게 다양한 서비스를 제공하는 웹 응용 프로그램을 개발하여 설치하는 것을 포함

### 웹 서버 소프트웨어
웹 브라우저로부터 요청을 해석하여 웹 문서를 전달하거나 적절한 웹 응용 프로그램을 작동시키고 실행 결과를 다시 전송하는 소프트웨어
예) Apache, nginx, IIS 등


## 웹 문서와 전자 문서의 차이
### 전자 문서(Electronic Document)
- 컴퓨터로 작성한 문서
- 여러 페이지로 구성되어있으나 보통 하나의 파일에 저장

### 웹 문서(Web Document)
- `HTML(HyperText Markup Language)`로 작성
- HTML 문서라고도 부름

### 전자 문서와 웹 문서의 차이점
- 웹 문서는 페이지 단위로 분할(= 웹페이지)
- 웹 페이지에는 텍스트만 담고 텍스트가 아닌 데이터는 별도 파일로 만들어 웹 페이지에서 파일의 이름이나 주소로 연결
- 웹 문서에서 웹 페이지 사이의 연결은 `하이퍼링크(Hyperlink)`를 이용
- 전자 문서는 문서를 읽는 순서를 문서 작성자가 정하지만, 웹 문서의 경우 사용자가 정함

`**하이퍼링크(Hyperlink)** 다른 웹 페이지나 이미지 주소를 가진 텍스트
웹 브라우저가 하이퍼링크를 클릭하면 해당 문서를 볼 수 있는 하이퍼텍스트 개념 구현`


## 웹 페이지의 주소 URL
- 웹 브라우저가 웹 사이트에 접속하면 웹 사이트는` 대표 웹 페이지`를 웹 브라우저에게 보낸다.
- 대표 웹 페이지(Defalt Webpage) 파일의 이름은 주로 index.html 혹은 default.html로 지정하는 편이다.

### 웹 페이지의 이름/주소
웹 서버의 주소 & 웹 페이지의 파일의 경로명으로 구성

### `URL(Uniform Resource Locator)`
#### 구성
<span style="background-color:#fff5b1">https://</span><span style="background-color:#FFE6E6">www.oracle.com</span><span style="background-color:#E6E6FA">:80</span><span style="background-color:#C0FFFF">/technetwork/java/</span><span style="background-color:#DCFFE4">index.html</span>

- <span style="background-color:#fff5b1">https://</span> 프로토콜
- <span style="background-color:#FFE6E6">www.oracle.com</span> 서버 주소
- <span style="background-color:#E6E6FA">:80</span> TCP/IP 포트 번호
- <span style="background-color:#C0FFFF">/technetwork/java/</span> 경로명
- <span style="background-color:#DCFFE4">index.html</span> 웹 페이지 파일 이름


## 웹 브라우저와 웹 서버 사이의 통신, `HTTP`
### HTTP 통신 과정
1. 클라이언트가 웹 서버에 연결 요청
2. 웹 서버의 연결 수락
3. 클라이언트가 HTML 페이지 요청
4. 웹 서버가 데이터베이스에서 HTML 페이지를 읽어옴
5. 웹 서버가 HTML 페이지를 클라이언트에게 전송
6. 클라이언트의 브라우저는 HTML 페이지를 해독 및 출력

* 1번에서 5번까지를 `HTTP 세션`이라고 함


# 웹의 시작과 성공
## 웹의 시작
`웹 문서`
- HTML 언어 기반의 텍스트 파일로 만듦
- 파일 내에 인터넷 주소로 다른 문서를 연결하는 하이퍼링크 삽입

## 웹의 성공
- 만들기 쉬운 HTML 문서
- 효율적인 HTTP 통신
- 클라이언트와 서버의 작업 분담



# 웹 페이지 구성
## 웹 페이지 구성 3요소
- 웹 페이지의 구조와 내용: `HTML` `태그`로 작성'
- 웹 페이지의 모양: `CSS(Cascading Style Sheet)`로 작성
- 웹 페이지의 행동 및 응용 프로그램: `JavaScript`로 작성

## HTML, CSS, JavaScript
- `HTML`: 웹 페이지의 구조와 내용
- `CSS`: 웹 페이지의 모양
- `JavaScript`: 웹 페이지의 동적 변경 및 응용 프로그램 작성