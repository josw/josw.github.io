# 왜 코루틴인가

https://kotlinlang.org/docs/async-programming.html#futures-promises-and-others

* 기존 비동기 프로세스
    * 스레드
        * 무겁다
        * 갯수가 제한적이다
        * 플렛폼에 제한이 있다
        * 디버깅, race condition 의 문제가 있다

    * 콜백
      * 코드가 복잡해진다
      * 에러 핸들링이 어렵다


  * Future, promises
    * 기존 소스를 많이 수정해야 함 
    * 러닝커브
    * 특정 리턴 타입 Promise?
    * 에러 핸들링이 어렵다

