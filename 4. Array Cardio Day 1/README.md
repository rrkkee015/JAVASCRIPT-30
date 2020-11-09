# 4. Array Cardio Day 1
## JavaScript Method
### Map
- `배열.map((요소, 인덱스, 배열) => { return 요소 });`
- map의 기본 원리는 반복문을 돌며 배열 안의 요소들을 1대1로 짝지어 주는 것이다.
  ```javascript
  const oneTwoThree = [1, 2, 3];
  let result = oneTwoThree.map((v) => {
    console.log(v);
    return v;
  });
  oneTwoThree === result; // false
  // map을 실행하는 배열과 결과로 나오는 배열이 다른 객체임을 알아야한다.
  result = oneTwoThree.map((v) => {
    return v + 1;
  });
  result; // [2, 3, 4]
  
  result = oneTwoThree.map((v) => {
    if (v % 2) {
      return '홀수';
    }
    return '짝수';
  });
  result; ['홀수', '짝수', '홀수'
  ```
### Reduce
- `배열.reduce((누적값, 현잿값, 인덱스, 요소) => { return 결과 }, 초깃값);`
- 이전 값이 아니라 누적값이라는 것을 알아야한다.
  ```javascript
  result = oneTwoThree.reduce((acc, cur, i) => {
    console.log(acc, cur, i);
    return acc + cur;
  }, 0);
  // 0 1 0
  // 1 2 1
  // 3 3 2
  result; // 6

  // 초깃값을 적어주지 않으면 자동으로 초깃값이 0번째 인덱스의 값이 된다.
  result = oneTwoThree.reduce((acc, cur, i) => {
    console.log(acc, cur, i);
    return acc + cur;
  });
  // 1 2 1
  // 3 3 2
  result; // 6

  // map 예제를 reduce로 만들 수 있다.
  result = oneTwoThree.reduce((acc, cur) => {
    acc.push(cur % 2 ? '홀수' : '짝수');
    return acc;
  }, []);
  result; // ['홀수', '짝수', '홀수']

  // 홀수만 필터링 할 때
  result = oneTwoThree.reduce((acc, cur) => {
    if (cur % 2) acc.push(cur);
    return acc;
  }, []);
  result; // [1, 3]

  // 비동기 처리할 때도 유리하다.
  const promiseFactory = (time) => {
    return new Promise((resolve, reject) => {
      console.log(time);
      setTimeout(resolve, time);
    });
  };
  [1000, 2000, 3000, 4000].reduce((acc, cur) => {
    return acc.then(() => promiseFactory(cur));
  }, Promise.resolve());
  // 바로 1000
  // 1초 후 2000
  // 2초 후 3000
  // 3초 후 4000
  // 초깃값을 Promise.resolve()로 한 후에, return된 프로미스에 then을 붙여 다음 누적값으로 넘기면 된다.
  ```
### Arrow Function
```javascript
(param1, param2, …, paramN) => expression // expression 그대로 리턴해줌
// 다음과 동일함:  => { return expression; }
```