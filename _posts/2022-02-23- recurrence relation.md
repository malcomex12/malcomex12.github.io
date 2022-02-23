---
layout: single
title: "2022-02-23-점화식"
---

## 점화식
점화식 (=재귀식)
-점화식이란 수열에서 이웃하는 두개의 항 사이에 성립하는 관계를 나타낸 관계식
-대표적인 점화식
    -등차수열
    -등비 수열
    -팩토리얼
    -피보나치 수열

점화식 예
f(1) = 3
f(2) =f(1)+2/ =3 + 2  = 5
f(3) =f(2)+2/ =5 + 2  = 7
f(4) =f(3)+2/ =7 + 2  = 9
f(5) =f(4)+2/ =9 + 2  = 11
f(n) = f(n-1)+2, f(1)=3


***

## 등차수열 예제

```javascript
//등차수열 예제 1
let result;

function forloop(s, t, number) {
    let acc = 0;

    for (let i = 1; i <= number; i++){
        if (i == 1)
            acc += s;
        else 
            acc += t;

        console.log(i, acc);
    }

    return acc;
}

result = forloop(3, 2, 5);
console.log(result);

//등차수열 (재귀)

let result;
function recursive(s, t, number) {
    //재귀가 멈추는 조건
    if (number == 1){
        return s;
    }

    //반복할 코드(메인로직)
    recursive(s, t, number - 1) + t;
    // number: 5 recursive(s, t, 4) + 2
    // number: 4 recursive(s, t, 3) + 2
    // number: 3 recursive(s, t, 2) + 2
    // number: 2 recursive(s, t, 1) + 2
    // number: 1 => 3

}

result = recursive(3, 2, 5);
console.log(result)
```
***

## 등비수열

```javascript
// 등비수열 예제 (for문)
let result;

function forloop(s, t, number){
    let acc =1;
    
    for (let i = 1; i <= number; i++) {
        if (i == 1)
            acc *= s;
        else
            acc *= t;

        console.log(i, acc)
    }

    return acc;
}

result = forloop(3, 2, 5);
console.log(result);

//등비수열 예제 (재귀함수)
let result;
function recursive(s, t, number) {
    if (number == 1) {
        return s;
    }

    return recursive(s, t, number - 1) * t;
}

result = recursive(3, 2, 5);
console.log(result); // output : 48
```

## 팩토리얼

```javascript
// 점화식 - 팩토리얼 예제
let result;

function recursive(number) {
    if (number == 1) {
        return number;
    }
    
    console.log(number)
    return recursive(number - 1) * number; 
}

result = recursive(5);
console.log(result); //output: 120
```

***

## 피보나치 수열
```javascript
/피보나치 수열 예제
// 피보나치 수열: 전항과 전전항의 합이 현재 항이다.
let result;

function recursive(number){
    if (number ==1 || number == 0){
        return number
    }
    console.log(number)
    //피보나치 수식: f(n) = f(n - 1) + f(n - 2)
    return recursive(number -1) + recursive(number - 2);
}

result = recursive(5)
console.log(result);
```

***
