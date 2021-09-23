# 문제52 : quick sort

다음 빈 칸을 채워 퀵 정렬을 완성해주세요.

```javascript
function quickSort(arr){
  if (arr.length <= 1){
    return arr;
  }

  const pivot = arr[0];
  const left = [];
  const right = [];

  for (let i=1; i<arr.length; i++){
      // 1번
      if(/*빈칸을 채워주세요*/){
        left.push(arr[i]);
      } else {
        right.push(arr[i]);
      }
  }

  //2번
  return /*빈칸을 채워주세요*/
}

const array = prompt('배열을 입력하세요').split(' ').map(n => parseInt(n, 10));

console.log(quickSort(array));
```

# 풀어보기

```javascript
function quickSort(arr) {
  if (arr.length <= 1) return arr;

  const pivot = arr[0];
  const left = [];
  const right = [];

  for (let i = 0; i < arr.length; i++) {
    // 1번
    if (arr[i] < pivot) {
      left.push(arr[i]);
    } else {
      right.push(arr[i]);
    }
  }
  // 2번 : left.concat으로 풀었어서 틀림!
  return quickSort(left).concat(pivot, right);
}

const array = prompt("배열을 입력하세요")
  .split(" ")
  .map((n) => parseInt(n, 10));

console.log(quickSort(array));
```
