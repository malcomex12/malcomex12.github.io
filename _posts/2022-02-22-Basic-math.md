---
layout: single
title: "2022-02-22-기본수학정리"
---

## 기본수학

/*
기본수학이론에서는
1. 알고리즘 복잡도
2. 경우의 수(순열과 조합)
3. 점화식
을 중점적으로 배울것이다.

1. 알고리즘 복잡도 (시간복잡도)

- 입력 크기의 값에 대해 단위 연산을 몇 번 수행하는지 계산하여, 알고리즘의
수행시간을 평가하는 방법.

- 3가지 접근적 표현법
    -빅오 : 최악의 상황을 고려하여 성능 측정 결과 표현.
    -세타 : 평균적인 경우에서의 성능 측정 결과 표현.
    -오메가: 최선의 상활일 때의 성능 측정 결과 표현.


2. 경우의 수
    -어떤 사건 혹은 일이 일어날 수 있는 경우의 가짓수를 수로 표현.
    -일상 생활에서의 경우의 수
        -주사위 : 던지는 결과, 1~6 사이의 숫자이므로 경우의 수는 6
        -윷 : 던지는 결과, 도,개,걸,윷,모 이므로 경우의 수는 5
        -가위바위보 : 게임 결과, 가위,바위,보 중에 하나를 낼 수 있으므로
                    경우의 수는 2
        -동전 : 던지는 결과, 앞,뒷면이므로 경우의수는 2

    -완전탐색으로 경우의 수를 푸는 알고리즘
        -순열:서로 다른 n개의 원소 중에서 r을 중복 없이 골라 순서에 상관있게
                나열하는 경우의 수
        -조합:서로 다른 n개의 원소 중에서 r을 중복 없이 골라 순서에 상관없이
                나열하는 경우의 수
        -중복 순열: 서로다른 n개의 원소중에서 r개를 중복 있게 골라 순서에 상관없이
                나열하는 경우의 수
    
    
3. 점화식
    -점화식(재귀식)이란 수열에서 이웃하는 두개의 항 사이에 성립하는 관계를
    나타낸 관계식
    -대표적인 점화식
        -a: 고정된 상수

        -등차수열:F(n)=F(n-1)+a
        -등비 수열:F(n)=F(n-1)*a
        -팩토리얼:F(n)=F(n-1)*n
        -피보나치 수열:F(n)=F(n-1)+F(n-2)
***

## 알고리즘 복잡도

/*
알고리즘 평가 지표
1. 정확성
2. 작업량
3. 메모리 사용량
4. 최적성
5. 효율성 (1.시간복잡도, 2.공간 복잡도)
*/


시간복잡도
 -입력 크기의 값에 대해 단위 연산을 몇 번 수행하는지 계산하여,
 알고리즘의 수행시간을 평가하는 방법

 - 3가지 접근적 표현법
    -빅오 : 최악의 상황을 고려하여 성능 측정 결과 표현.
        -예제1 : 
        function bit_o(n){
            let sum = 0;    1회
            sum = n * 2;    1회
            return sum;     1회
        }
        -예제2 : 
        function bit_o(arr, n){
            let sum = 0;                    1회
            for(let i = 0; i < n; i++){      n회      
            sum = n * 2;}                    1회
            return sum;                     1회
        }
        -예제3 : 
        function big_o(arr, n){
            let sum = 0;                        1회

            for (let i = 0; i < n; i++){
                for(let j = 0; j < n; j++){     n*n =n²
                    sum += arr[i][j]
                }
            }
            return sum;                         1회
                                                n² + 2 =>(N²)
        }

        -예제4 :
        function bit_o(n) {
            let sum = 0;                        1회
            for (let i = 0; i < n; i*=2){
                sum+=2;                         n/2회
            }
            return sum                          1회

                                                n/2 + 2 =>O(log N)
        }

    -세타 : 평균적인 경우에서의 성능 측정 결과 표현.
    -오메가: 최선의 상활일 때의 성능 측정 결과 표현.
***

## 경우의 수

2. 경우의 수
    -어떤 사건 혹은 일이 일어날 수 있는 경우의 가짓수를 수로 표현.
    -일상 생활에서의 경우의 수
        -주사위 : 던지는 결과, 1~6 사이의 숫자이므로 경우의 수는 6
        -윷 : 던지는 결과, 도,개,걸,윷,모 이므로 경우의 수는 5
        -가위바위보 : 게임 결과, 가위,바위,보 중에 하나를 낼 수 있으므로
                    경우의 수는 2
        -동전 : 던지는 결과, 앞,뒷면이므로 경우의수는 2

    -완전탐색으로 경우의 수를 푸는 알고리즘
        -순열:서로 다른 n개의 원소 중에서 r을 중복 없이 골라 순서에 상관있게
                나열하는 경우의 수( nPr)
        -조합:서로 다른 n개의 원소 중에서 r을 중복 없이 골라 순서에 상관없이
                나열하는 경우의 수( nCr)
        -중복 순열: 서로다른 n개의 원소중에서 r개를 중복 있게 골라 순서에 상관없이
                나열하는 경우의 수(nH)
***

## 순열
### P.S 개어려우니까 꼭 다시보기
/*
순열
1. 서로 다른 n개의 원소 중에서 r을 중복없이 골라 순서에 상관있게 나열하는 경우의 수
2. 3개의 알파벳으로 단어를 만드는 경우의 수
        => A B C => 1. A B C / 2. A C B
A,B,C   => B A C => 1. B A C / 2. B C A
        => C A B => 1. C A B / 2. C B A
*/

```javascript
//순열예제 (for 문 사용)
// let input = ["a", "b", "c"];
// let count = 0;

// function permutation(arr) {
//     //for i = 첫번째 index 위치시킬 요소 a, b, c [i, 0, 0]
//     for (let i =0; i < arr.length; i++){
//         //for j = 두번째 index 위치시킬 요소  [i, j, 0]
//         for ( let j = 0; j < arr.length; j++) {
//             if (i == j) continue;//같을경우 스킵처리
//             //for k = 세번째 index 위치시킬 요소. [i, j, k]
//             for (let k = 0; k < arr.length; k++){
//                 if (i == k) continue;
//                 if (j == k) continue;

//                 console.log(arr[i], arr[j], arr[k])
//                 count++;
//             }
//         }
//     }
// }

// permutation(input);
// console.log(count);
```
```javascript
// 순열 예제 (재귀함수사용)
//s = 배열의 start 위치, r = 몇번 돌릴것인지. 이번에 2를 넣은이유는 a,b,c, 0,1,2 세가지라
let input = ["a", "b", "c"];
let count = 0;


function permutation_func(arr, s, r) {
    //1. 재귀함수를 멈춰야할 조건
    if (s == r) {
        count++
        console.log(arr.join(" "));
        return
    }
    //재귀를 돌면서 변경되어야 할 부분/메인로직
    for (let i = s; i < arr.length; i++) {
        [arr[s], arr[i]] = [arr[i], arr[s]];//스왑
        permutation_func(arr, s + 1, r);
        [arr[s], arr[i]] = [arr[i], arr[s]]// 원상복귀
        /*
        s = 0, r = 2 ["a",]
        s = 1, r = 2, i = 1 ["a", "b",]
        s = 2, r = 2, ["a", "b", "c"]
        ...
        s = 1, r = 2, i = 2 ["a", "c",]
        s = 2, r = 2, ["a", "c", "b"]
           s = 1, r = 2, i = 2 ["a, b,"]
        ...
        */
    }
}
permutation_func(input, 0, 2);
console.log(count)

/*
output:
a b c
a c b
b a c
b c a
c b a
c a b
6
*/
```
***
## 조합
조합
서로 다른 n개의 원소 중에서 r을 중복 없이 골라 순서에 상관없이 나열하는
경우의수
***

## 예제
4개의 숫자카드에서 2개를 뽑는 경우의 수

```javascript
1234 => 1 => 1,2 / 1,3 / 1, 4
     => 2 => 2,3 / 2,4
     => 3 => 3,4 

*/
예제 (for 문)
 let input = [1, 2, 3, 4] //4C2
 let count = 0;

 function combination(arr){
     //for문의 개수 => 뽑는 개수 ==> r 2
     for( let i = 0; i < arr.length; i++){
         for ( let j = i+1; j < arr.length; j++){
             count++
             console.log(arr[i], arr[j])
         }
     }
 }
 combination(input)
 console.log(count)


//예제 (재귀함수)
let input = [1, 2, 3, 4] //4C2
let output = [];
let count = 0;

function combination(arr, data, s, idx, r) {
    if (s == r) {
        count++
        console.log(data);
        return;
    }

    for (let i = idx; arr.length - i >= r - s; i++) {
        data[s] = arr[i];
        combination(arr, data, s + 1, i + 1, r);

    }
}

combination(input, output, 0, 0, 2);
console.log(count);

```
