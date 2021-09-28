# 문제65 : 변형된 리스트

a = [1, 2, 3, 4]
b = [a, b, c, d]
이런 리스트가 있을 때 **[[1, a], [b, 2], [3, c], [d, 4]]** 이런 식으로 a, b 리스트가 번갈아가면서 출력되게 해주세요.

# 풀어보기

```js
let a = [1, 2, 3, 4];
let b = ["a", "b", "c", "d"];
let answer = [];

for (let i = 0; i < a.length; i++) {
  // 0, 2번째 -> [1,a], [3,c]가 나와야 할 때
  if (i % 2 == 0) {
    answer.push([a[i], b[i]]);
  } else {
    // b의 원소가 먼저 나와야 할 때
    answer.push([b[i], a[i]]);
  }
}
console.log(answer);
```

# 답안

방법1. forEach 사용

```js
let a = [1, 2, 3, 4];
let b = ["a", "b", "c", "d"];
let answer = [];

a.forEach(function (val, index) {
  if (index % 2 === 0) {
    // a원소 먼저
    answer.push([val, b[index]]);
  } else {
    // b 원소 먼저
    answer.push([b[index], val]);
  }
});

console.log(answer);
```

방법2. map 사용

```js
let a = [1, 2, 3, 4];
let b = ["a", "b", "c", "d"];

let answer = a.map(function (val, index) {
  if (index % 2 === 0) {
    return [val, b[index]];
  } else {
    return [b[index], val];
  }
});

console.log(answer);
```
