---
layout: single
title: "연산자 정리"
---

#모든 기본 연산자 정리

1. 증감연산자
2. 논리연산자
3. 비교연산자
4. 복합대입 연산자
5. 3항 연산자 


##증감연산자

```javascript
let num, result;

num = 10;
/* num뒤에 ++를 쓰게되면 선 복사 후 증감이 되는 방식이다.
다음행에 ++가 적용된다*/
result = num++; // outfoot= 10
console.log(result);
console.log(num);

num = 10; 
/* num앞에 ++를 쓰게되면 증감 후 복사가 되는 방식이다.
이번행에 ++가 적용된다*/
result = ++num; // outfoot=  11
console.log(result);
console.log(num);

num = 10;
result = num--; // outfoot=  10
console.log(result);
console.log(num);

num = 10;
result = --num; // outfoot=  9
console.log(result);
console.log(num);
```
<br>
<hr>
<br>
##논리연산자

```javascript

//논리연산자: &&(AND), ||(OR), !(NOT)

//a && b (a가 b 보다 작으면 true 아니면 false) 
// a,b 둘 중 하나라도 false이면 false

//a || b (a가 b보다 크면 true 아니면  false)
//둘 중 하나라도 true 이면 값은 true

//!a (a가 b보다 크거나 같으면 true 아니면 false) 부정

console.log(true || false); // output: true

console.log(Boolean(0 || false)); // output: false

console.log(Boolean(123 || false)); //output: true

console.log(Boolean(123 && 0)); //output: false

console.log(Boolean(false && true)); //output: false

console.log(Boolean(true && 3)); //output: true

console.log(Boolean(0 && false)); //output: false

console.log(Boolean(!false)); //output: true

console.log(Boolean(!123)); //output: false
```
<br>
<hr>
<br>

##비교연산자
단순한 비교 연산자이다.

```javascript
console.log("Z" > "A");

console.log("hello" < "hi");

console.log("Hello" >= "Helloo");

console.log("5" <= 10);

console.log(true == 1); 

console.log(false != 123); //!는 부정표현 Ex) !=는 같지않다.

console.log(true === 1);

console.log(false !== 123);
```
<br>
<hr>
<br>
##복합대입연산자

```javascript
let num = 10;

let result_1,  result_2, result_3, result_4, result_5;
result_1 = result_2 = result_3 = result_4 = result_5 = 31;

//복합 대입 연산자: +=
result_1 += num; //result_1 = result_1 + num = 41
console.log(result_1);

//복합 대입 연산자: -=
result_2 -= num; // result_2 = result_2 - num = 21
console.log(result_2);

//복합 대입 연산자: *=
result_3 *= num;  // result_3 = result_3 * num = 310
console.log(result_3);

//복합 대입 연산자: /=
result_4 /= num;  // result_4 = result_4 / num = 3.1
console.log(result_4);

//복합 대입 연산자: %=(나머지 연산자)
result_5 %= num;  //result_5 = result / num 의 나머지
console.log(result_5);

```
<br>
<hr>
<br>

##3항 연산자

```javascript
let age = 20;
//일반 조건문
if (age < 19) {
    msg = "The user is not an adult.";
}

else{
    msg = "The user is an adult.";
}

console.log(msg);

//3항 연산자

msg_another = age < 19 ? "The user is not an adult." : "The user is an adult."

// =변수 = 조건문 ? true일때 변수에 저장 : false 일때 변수에 저장

console.log(msg_another);

// P . S ?는 참, !는 부정
```
