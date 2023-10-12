# 38-01-Requset-And-Response

- 브라우저의 기능은 필요한 자원을 서버에 잘 요청하고 잘 응답 받아서 화면에 렌더링 하는 것이다.
- 서버에 요청을 전송하기 위해서 브라우저는 주소창을 제공한다.

### 브라우저 주소창 과정 간단 ver

1. 주소창에 URL 입력
2. URL의 호스트 이름이 DNS를 통해 IP주소로 변환
3. 해당 IP주소를 갖는 서버에게 요청 전송

### 브라우저 주소창 과정 예시 ver

1. https://www.naver.com 을 입력하고 엔터 키를 누른다.
   1. 루트요청 (/. 스키마(https), 호스트(www.[naver.com](http://naver.com)) 로만 구성된 URI에 의한 요청)이 naver.com 서버로 전송
   2. 루트 요청에는 리소스를 요청하는 내용이 없지만 암묵적으로 index.html 응답 하도록 기본 설정
   3. 즉 htts://www.naver.com === htts://www.naver.com/index.html
2. 서버는 루트 요청에 따라 서버의 루트 폴더에 존재하는 정적 파일을 index.html을 브라우저로 응답
   1. 만약! index.html 같은 정적 파일을 원하지 않으면 다른 정적 파일 경로와 파일이름을 URI의 호스트 뒤의 path에 적어 요청한다.
      ex) htts://www.naver.com/assets/data/data.json
   2. JS를 통해서 동적으로 정적/동적 데이터를 요청 할 수 있다. ⇒ 42.ajax, 44.REST API 참고

- 실제로 www.naver.com 을 주소창에 입력해보면 html 말고도 요청하지도 않은 파일들(css, js, 이미지, 폰트, 어쩌고 저쩌고) 이 많다.
  - 그건 브라우저 렌더링 엔진이 html을 파싱하면서 css를 로드하는 `link` , 자바스크립트를 로드하는 `script` 태그 이미지 파일을 로드하는 `img` 태그를 만나 html 파싱을 일시 중단하고 해당 자원을 서버에 요청하기 때문이다.
