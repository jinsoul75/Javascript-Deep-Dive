# 38-09-Async-And-Defer-Attribute

- JS 파싱에 의한 돔 생성 중단 문제를 해결하기 위해 HTML5부터 script 태그에 `async` `defer` 속성이 추가되었다.
- src 속성을 통해 외부 JS 파일을 로드하는 경우 쓸 수 있다.
    - 인라인 JS에는 못쓴다.
- `async` `defer` 둘 다 HTML 파싱과 JS 파일 로드가 **비동기적**으로 동시에 진행된다는 공통점이 있다.

## Async

- JS의 파싱과 실행은 JS파일 로드(HTML 파싱과 동시에 진행) 끝나고 진행
    - 이때 HTML 파싱이 중단된다.
- 먼저 로드가 끝난 JS부터 실행되어서 순서 보장이 되지 않는다.

### Defer

- HTML 파싱이 끝나고 난 뒤 JS 파싱과 실행
- script 태그 순서에 따라 실행되므로 순서 보장이 된다.