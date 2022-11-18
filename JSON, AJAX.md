>## JSON
>```
>javascript object notation : 자바스크립트 ★사전★ 형식 파일
>```
>JSON
>```
>'{ "키1": "값1", "키2": "값2", ..., "키n": "값n"}'
>```
+ 사전 -> JSON
    ```angular2html
    JSON.stringify(사전_변수);
    ```
+ JSON -> 사전
    ```angular2html
    JSON.parse(사전_변수);
    ```

---
>## AJAX
>```
>Asynchronous Javascript And XML : 비동기 자바스크립트와 XML
>
>즉, 서버와 통신하기 위해 XHLHttpRequest 객체를 사용하는 것
>```
>```
>페이지 새로고침 없이 
>사용자가 서버에 데이터(XML, JSON, HTML, ...) 요청한 후
>서버에서 데이터를 받고 작업을 수행
>```
>``검색어 자동완성``, ``장바구니 아이템 추가``, ....
>```
>동기 : 서버에 신호를 보냈을 때, 응답이 돌아와야 다음 동작 실행
>
>비동기 : 서버에 신호를 보냈을 때, 응답 상태와 상관없이 다음 동작 실행 
>```

### 사용자(client) -> 서버(server)
+ 데이터 전송 객체 생성
    ```angular2html
    let 객체_변수 = new XHLHttpRequest();
    ```
+ 데이터 전송 방식
    ```
    객체_변수.open("GET/POST", 요청_경로);
    
    GET : 주소창에 입력내용 보임
    POST : 주소창에 입력내용 숨김
    ```
+ 데이터 전송
    ```
    객체_변수.send();
    ```
  
### 서버(server) -> 사용자(client) 
+ 데이터 응답 함수
    ```angular2html
    객체_변수 = onreadystatechange = ( 매개변수1, ..., 매개변수n ) => {
        if ( 객체_변수.readyState == 4 ) {
            if ( 객체_변수.status == 200 ) {
                } else {
            }
        }
    }
    ```

  + readyState : 데이터 전송 상태
      ```
      0 : 객체 생성 & 방식 X
      1 : 방식 O & 전송 X
      2 - 요청 O & 전송 X
      3 - 전송 중
      4 - 전송 완료
      ```
    
  + status : 데이터 응답 상태
      ```
      200 : 응답 성공
      404 : 응답 데이터 없음
      500 : 서버 오류
      ```
