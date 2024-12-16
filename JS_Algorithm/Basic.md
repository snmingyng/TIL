# 1. 변수 선언
## var
+ __중복 선언 가능__ 
+ __재선언 가능__: 마지막에 할당된 값이 최종 변수에 저장, 이를 보완하기 위한 변수 선언 방식이 let과 const 
+ __스코프__: 함수 내에서 선언된 변수는 함수 내에서만 유효, 함수 내라면 블록은 상관 없다.


## let
+ __중복 선언 불가__: 중복선언 시 에러 발생
+ __재할당 가능__: 변수에 값을 재할당하는 것이 가능하다
+ __스코프__: 함수나 for, while, try/catch문 등 코드 블록 내부에서 선언된 변수는 블록 내부에서만 유효하다. 블록 외부로부터 참조도 불가하다. (ex: for문에서 선언된 let i)

## const
+ __중복 선언 불가__
+ __재할당 불가__
+ __스코프__: let과 동일  


# 2. 스프레드 연산자(...)
배열, 함수, 객체 등에 활용 가능  
## 배열에서의 활용 
[참고 링크](https://growing-jiwoo.tistory.com/35)  
[얕은 복사/깊은 복사 참고](https://likedev.tistory.com/entry/Javascript-%EB%B0%B0%EC%97%B4-%EB%B3%B5%EC%82%AC%ED%95%98%EB%8A%94-%EC%97%AC%EB%9F%AC%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC)

```js
// ES6 spread operator
let arr1 = ['apple','banana']; 
let arr2 = [...arr1]; 

arr2.push('orange'); 

console.log(arr2); // [ "apple", "banana", "orange" ]

// 원본 배열은 변경되지 않습니다.
console.log(arr1); // [ "apple", "banana" ]
```

# 3. 삼항연산자
```js
condition ? exprIfTrue : exprIfFalse;
//조건문 ? 참일 때 실행: 거짓일 때 실행
```

