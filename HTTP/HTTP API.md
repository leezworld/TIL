# HTTP API

### **HTTP API 데이터 전송**

1. 서버 to 서버
   - 백엔드 시스템 통신

<br>

2. 앱 클라이언트
   - 아이폰, 안드로이드

<br>

3. 웹 클라이언트
   - HTML에서 Form 전송 대신 자바 스크립트를 통한 통신에 사용(AJAX)

<br>

4. POST,PUT,PATCH : 메세지 바디를 통해 데이터 전송

<br>

5. GET : 조회, 쿼리 파라미터로 데이터 전달

<br>

6. Content-Type:application/json을 주로 사용(사실상 표준)
   - TEXT, XML, JSON 등등
     <br>
     <br>
     <br>

### **HTTP API 설계**

1. HTTP API - **컬렉션 (POST 기반)**

   - 예 ) 회원 관리 API 제공

   <br>

2. HTTP API - **스토어 (PUT 기반)**
   - 예 ) 정적 컨텐츠 관리, 원격 파일 관리

<br>

3. HTML FORM 사용
   - 예 ) 웹 페이지 회원 관리

<br>

- **POST기반과 PUT기반 신규 자원 등록 특징**

  - POST
    - 클라이언트는 등록될 리소스의 URI를 모른다.
    - 서버가 새로 등록된 리소스 URI를 생성해준다.
    - **컬렉션(Collection)**
      - 서버가 관리하는 리소스 디렉토리
      - 서버가 리소스의 URI를 생성하고 관리

   <br>

  - PUT
    - 클라이언트가 리소스 URI를 알고 있어야 한다.
    - 클라이언트가 직접 리소스의 URI를 지정한다.
    - **스토어(Store)**
      - 클라이언트가 관리하는 리소스 저장소
      - 클라이언트가 리소스의 URI를 알고 관리

<br>

- **HTML FORM 사용**
  - HTML FORM은 **GET,POST**만 지원
  - **컨트롤 URI** : 제약이 있기 때문에 HTTP 메서드로 해결하기 애매한 경우

<br>

### **URI 설계 개념 정리**

<br>

- 문서(document)
  - 단일 개념(파일 하나, 객체 인스턴스, 데이터베이스 row)
  - 예) /members/100, /files/star.jpg

<br>

- 컬렉션(collection)

  - 서버가 관리하는 리소스 디렉터리
  - 서버가 리소스의 URI를 생성하고 관리
  - 예) /members

<br>

- 스토어(store)

  - 클라이언트가 관리하는 자원 저장소
  - 클라이언트가 리소스의 URI를 알고 관리 -예) /files

<br>

- 컨트롤러(Controller), 컨트롤 URI
  - 문서, 컬렉션, 스토어로 해결하기 어려운 추가 프로세스 실행
  - 동사를 직접 사용
  - 예) /members/{id}/delete
