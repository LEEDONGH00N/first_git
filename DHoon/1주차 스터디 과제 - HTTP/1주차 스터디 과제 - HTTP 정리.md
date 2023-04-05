# 1주차 스터디 과제 - HTTP 정리

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled.png)

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%201.png)

## HTTP (HyperText Transfer Protocol)

: 브라우저에서 URL이라는 주소 양식을 통해서 클라이언트와 서버가 통신하는 규칙

- Protocol : 규칙
- HyperText : 다른 리소스 혹은 페이지로 이동할 수 있는 링크

<aside>
ℹ️ HTTP를 이용한 일반적인 흐름
**클라이언트의 REQUEST → 서버의 RESPONSE 전송**

</aside>

<aside>
❓ HTTP HTTPS의 차이?

- HTTP의 약점
    - 암호화하지 않았기 때문에 보안에 취약함
    - 통신상대를 확인하지 않기 때문에 신뢰성이 떨어짐
- HTTPS = HTTP + SSL(암호화 기반 인터넷 프로토콜
    - 보안의 강화
    - 검색엔진 최적화
</aside>

### URL

- https://
    - 프로토콜
        - 통신 규칙
        - HTTP(HTTPS), FTP(파일 시스템 조회)
- www.google.com
    - 호스트
        - 서버의 주소
        - google.com을 호스트 네임이라고 지칭
- /search
    - 경로(path)
        - 호스트 내 서비스의 위치
        - 서비스 별로 분할(검색, 회원)
- ?q=techit
    - 쿼리 문자열
        - ? 기호로 시작, &로 연결
        - 키/값 쌍으로 구성

## HTTP의 Request 내용

: 웹 브라우저에서 웹 사이트를 로드하는 데 필요한 정보를 요청하는 방법

1. HTTP version type(0.9, 1.0, 1.1, 2.0)
2. URL
3. HTTP Method
4. HTTP request Header
5. HTTP Body

### 1. HTTP Method

: 클라이언트가 서버에게 사용자 요청의 목적이나 종류를 알리는 수단

- **GET**
    - 리소스 조회
    - 쿼리를 통해 서버에 데이터 전달

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%202.png)

- **POST**
    - 요청 데이터처리(주로 데이터 등록에 사용)
    - 메세지 BODY를 통해 서버에 요청 데이터 전달
    - 주로 **신규 리소스** 처리에 이용
    
    ![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%203.png)
    
    - 서버는 신규 리소스 생성
    
    ![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%204.png)
    
    - 서버는 신규 리소스 생성 후 응답 데이터를 보냄
    
    ![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%205.png)
    
- PUT
    - 리소스를 대체
        - 해당 리소스가 없으면 생성
        - 해당 리소스가 있으면 대체
    - POST와 달리 클라이언트가 리소스의 위치를 알고 URI 지정

**리소스가 있을 때**

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%206.png)

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%207.png)

**리소스가 없을 때**

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%208.png)

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%209.png)

**주의사항**

**리소스를 완전히 대체함**

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%2010.png)

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%2011.png)

- PATCH
    - 리소스의 일부만 변경
- DELEATE
    - 리소스 삭제

> HTTP Method를 왜 쓸까?
좋은 URI 설계는 리소스 식별이 잘 되어야 함
> 

나쁜 예

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%2012.png)

좋은 예

![Untitled](1%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%20%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A6%20-%20HTTP%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20f234e18bec9f4bdfa3ca82c794732e95/Untitled%2013.png)

→ 리소스와 행위를 분리

- 리소스 : 바우처
- 행위 : 조회, 등록, 삭제, 수정…

### 2. HTTP Request Header

: 클라이언트와 서버가 요청 또는 응답으로 정보를 전송하는 것

헤더의 종류

- General Header (공통 헤더)
    - 응답/요청 에 대한 추가 정보
- Request Header (요청 헤더)
    - 요청에 대한 추가 정보
- Response Header (응답 헤더)
    - 응답에 대한 추가 정보
- Entity Header (엔티티 헤더)
    - 리소스의 BODY에 대한 정보

### HTTP Request Body

: 요청에서 전송되는 정보의 body를 포함하는 부분

## HTTP의 응답 내용

1. HTTP state code
2. HTTP Response Header
3. HTTP Body

### 1. HTTP state code

HTTP 요청이 성공적으로 완료되었는지 여부를 확인하는 코드

1. 1XX → Informational
2. 2XX → Success
3. 3XX → Redirection
4. 4XX → Client Error
5. 5XX → Server Error

### 2. HTTP Response Header

: 응답 본문에서 전송되는 중요한 정보를 전달하는 헤더가 함께 제공

- 'GET'요청에 대한 성공적인 HTTP 응답 → 요청된 정보가 body에 포함
- 대부분의 웹 요청의 경우 이는 웹 브라우저에서 웹 페이지로 변환되는 HTML 데이터