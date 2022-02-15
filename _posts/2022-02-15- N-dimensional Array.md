---
layout: single
title: "N차원 Array"
---

## p.s 개념만 알고 주말에 복습

N차원 Array란
N차원 배열
배열 안에 N개 만큼의 배열이 존재하는 객체.
2/3차원 지도 정보, rgb를 저장하는 2차원 사진 파일 등을 표현할때 활용가능*/
```javascript
array = [[123],[456],[789]] 각 배열 안에있는 개수는 동일해야한다
array [3][3]
```
***

## 기본예제
```javascript
let array = [
    [101, 102, 103],
    [201, 202, 203],
    [301, 302, 303],
];

console.log(array);             //output:   [ [ 101, 102, 103 ], [ 201, 202, 203 ], [ 301, 302, 303 ] ]
console.log(array[0]);          //output:   [ 101, 102, 103 ]
console.log(array[1][0]);       //output:   201
console.log(array[2][2]);       //output:   303

let arr_2 = array.pop();
console.log(array.length); //output: 2
console.log(arr_2); //output: [ 301, 302, 303 ]
console.log(array); //output: [ [ 101, 102, 103 ], [ 201, 202, 203 ] ]

let array_num = array.push([401, 402, 403]);
console.log(array.length); //output: 3
console.log(array_num); //output: 3
console.log(array); //output: [ [ 101, 102, 103 ], [ 201, 202, 203 ], [ 401, 402, 403 ] ]

```
