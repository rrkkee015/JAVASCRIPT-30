# 6. Ajax Type Ahead
## 1장부터 지금까지 강의 중 가장 중요한 강의
## Fetch
- Fetch를 사용하는데 `fetch(url);`을 해서 반환 받는 값이 Promise 객체이다.
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