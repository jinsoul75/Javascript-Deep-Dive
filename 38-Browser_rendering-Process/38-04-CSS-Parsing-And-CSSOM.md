# 38-04-CSS-Parsing-And-CSSOM

- 렌더링 엔진은 HTML을 한줄씩 파싱하면서 DOM을 생성해 가다가
    - CSS를 로드하는 link 태그나 style 태그를 만나면 파싱을 일시 중단
    - link 태그의 href에 지정된 CSS 파일을 서버에 요청하여 로드한 CSS파일 이나 style 태그 내의 CSS를 HTML과 동일한 과정으로 파싱되어 CSSOM을 생성한다.