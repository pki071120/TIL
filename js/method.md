## Javascript 메서드

### 🍕 filter(item)
``` js
filter(item)
//filter(요소)
```
주어진 함수에 만족하는 요소들을 모아 새 배열로 반환시킨다.
``` js
let arr = [1,2,2,3,3,3,4];
arr.filter(el => el === 2); // [2,2]
```

### 🍕 includes()
``` js
includes(item)
//includes(요소)
```
함수 내의 요소를 포함하면 true를 반환, 포함하지 않는다면 false를 반환한다.
``` js
// ex
let str = "abcdef"
let arr = [1,2,3,4];

str.includes("cd"); //ture
arr.includes(5); //false
```

### 🍕 map()
``` js
map((item, index, arr))
//map(요소, 인덱스, 배열)
```
  배열의 각 요소에 접근하여 함수를 실행시킨 새로운 배열을 반환한다.

``` js
// ex
let arr1 = [0,9,8,7,6];
let arr2 = ["a","b","c","d","e"];
let total = 0;
let string = "";

arr1.map((item, index) => {
  index % 2 == 0 ? total += item;
}) //total = 14
arr2.map(item => {
  string += item;
}) //abcde
```

### 🍕 reduce()
``` js
reduce(callback(accumulator, currentValue, index, array), initialValue);
//reduce((누적값, 현재값, 인덱스, 요소), 초기값)
```
배열의 요소를 순차적으로 순회하며 숫자든 배열이든 객체든 하나의 값으로 줄여 반환시킨다.
초기값을 지정시킬 수 있다.
``` js
let arr = [1,2,3,4,5];

arr.reduce((acc, cur) => acc+cur);// 15
arr.reduce((acc, cur) => acc+cur, 1);// 16
```