# 6. Ajax Type Ahead
## 1장부터 지금까지 강의 중 가장 중요한 강의
## Fetch
- 네트워크 요청은 다음과 같다.
  - 주문 전송
  - 사용자 정보 읽기
  - 서버에서 최신 변경분 가져오기
  - 등등
- Fetch를 사용하는데 `let promise = fetch(url, [options]);`을 해서 반환 받는 값이 Promise 객체이다.
  - options에 아무것도 넘기지 않으면 요청은 `GET` 메서드로 진행된다.
  ```javascript
  let response = await fetch(url);

  if (reponse.ok) {
    let json = await response.json(); // 파싱도 기다려야함
  } else {
    alert("HTTP-ERROR: " + response.status);
  }

  // awiat 없는 버전
  fetch(url).then(response => {
    let json;
    if (response.ok) {
      response.json().then(data => json = data);
    } else {
      alert("HTTP_ERROR: " + response.status);
    }
  })
  ```
- 그래서 `fetch(url).then(blob => ())`으로 data를 받아와서 콜백함수를 할 수 있다.
- `blob`은 response를 가져온다.
```javascript
function displayMatches() {
  console.log(this.value);
  // 이런 식으로 하면 querySeletor html tag 내용을 가져올 수 있다.
}

const searchInput = document.querySeletor('.search');

searchInput.addEventListner('change', displayMatches);
```