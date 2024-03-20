## Javascript 메서드

### 🍕 filter()
``` js
let arr = [1,2,2,3,3,3,4];
arr.filter(el => el === 2); // [2,2]
```
주어진 함수에 만족하는 요소들을 모아 새 배열로 반환시킨다.

### 🍕 includes()
``` js
let str = "abcdef"
let arr = [1,2,3,4];

str.includes("cd"); //ture
arr.includes(5); //false
```
함수 내의 요소를 포함하면 true를 반환, 포함하지 않는다면 false를 반환한다.

### 🍕 map()
``` js
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
배열의 각 요소에 접근하여 함수를 실행시킨 새로운 배열을 반환한다.