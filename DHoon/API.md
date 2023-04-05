# 1주차 스터디 과제 - API

- REST / RESTful
    - REST : 웹에서 데이터를 전송하고 처리하는 방법을 정의한 인터페이스
        1. HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
        2. HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해
        3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미합니다
        
        **웹의 모든 자원에 고유한 ID인 HTTP URI 를 부여한다.**
        
        - 구성요소
            - 자원 : URI
            - 자원에 대한 행위 : HTTP Method(POST, GET, PUT, DELETE)
            - 자원에 대한 행위의 내용
    - RESTful : REST API의 셜계규칙을 따르는 시스템
    - REST API
        - URL에선 동사를 쓰지 않는다(명사만)
        - 마지막에 / 미포함
        - 언더바 대신 하이픈
        - 파일 확장자는 미포함
        - 행위를 포함하지 않는다
- Path Variable
    - 쿼리스트링으로 전달되는 경우 외에 URI에 전달되는 값을 받아오는 역할
- Query Parameter
- Path Variable과 Query Parameter는 각각언제 사용하는가?
- Domain
    - 

- API
    - API란?
        - 프로그램들이 서로 소통하는 방법
        - 프론트엔드가 벡엔드에게 요청할 때의 규칙
        - 서버에서 만듦
        - 데이터 서버를 갖고 있는 사람들이 원하는대로 디자인 가능
    - API 가이드
        - 요청
            - 주소
            - 전송방식(get / post)
            - 보낼 것 (query, sort, target)
        - 응답
            - 형식 : JSON(자바스크립트 오브젝트 노테이션 : 키-값의 패턴으로 표현), XML
            - 응답 의미 설명