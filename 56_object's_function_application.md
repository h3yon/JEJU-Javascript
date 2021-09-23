# 문제56 : 객체의 함수 응용

다음의 객체가 주어졌을 때 한국의 면적과 가장 비슷한 국가와 그 차이를 출력하세요.

```javascript
데이터
nationWidth = {
     'korea': 220877,
     'Rusia': 17098242,
     'China': 9596961,
     'France': 543965,
     'Japan': 377915,
     'England' : 242900,
}

출력
England 22023
```

# 풀어보기

```javascript
let nationWidth = {
  "korea": 220877,
  "Rusia": 17098242,
  "China": 9596961,
  "France": 543965,
  "Japan": 377915,
  "England": 242900,
};
let target = nationWidth["korea"];
delete nationWidth["korea"];

// entries()를 사용해 for of문으로 쉽게 키,값 에 접근할 수 있다.
// map일 때는 map1.entries, Object일 때는 Object.entries(nationWidth)
let keys = Object.keys(nationWidth);
let values = Object.values(nationWidth);

// Math.max.apply(null, arr) 알아두기
let gap = Math.max.apply(null, values);
let item = {};

function sol() {
  let temp = 0;
  for (let i in values) {
    temp = Math.abs(values[i] - target);
    if (gap > temp) {
      gap = temp;
      item["nation"] = keys[i];
      item["gap"] = gap;
    }
  }
  console.log(item.nation, item.gap);
}
```

# 답안

```javascript
const nationWidth = {
  "korea": 220877,
  "Rusia": 17098242,
  "China": 9596961,
  "France": 543965,
  "Japan": 377915,
  "England": 242900,
};

const w = nationWidth["korea"];

delete nationWidth["korea"];

const entry = Object.entries(nationWidth);
const values = Object.values(nationWidth);

//gap에 최댓값 저장
let gap = Math.max.apply(null, values);
let item = [];

for (let i in entry) {
  if (gap > Math.abs(entry[i][1] - w)) {
    gap = Math.abs(entry[i][1] - w);
    item = entry[i];
  }
}

console.log(item[0], item[1] - w);
```
