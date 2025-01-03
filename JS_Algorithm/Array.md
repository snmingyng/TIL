# 1. Array
## 유용한 메서드
### __array.length__: 배열의 길이 반환

## 추가/제거/교체
[온갖 메서드 짬뽕해서 푸는 문제 꼭 정리해놓을 것](https://school.programmers.co.kr/learn/courses/30/lessons/120844)
### __array.push()__: 배열의 끝에 요소를 추가
### __array.unshift()__: 새로운 요소를 배열의 맨 앞에 추가하고 새로운 길이를 반환
### __array.shift()__: 배열의 첫번째 요소를 제거하고 그 요소를 반환
### __array.pop()__: 배열의 마지막 요소를 제거하고 그 요소를 반환 
### __array.splice__: 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경
```js
 array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
// []: 생략 가능
```
start: 배열의 변경을 시작할 인덱스 지정  
deleteCount: 배열에서 제거할 요소의 수  
item: 추가할 요소
```js
const arr = ['A', 'C', 'D', 'F'];
arr.splice(1, 0, 'B');
console.log(arr);   //['A', 'B', 'C', 'D', 'F']
```
## 반전
### __array.reverce()__: 배열의 순서 반전

## 문자열 반환
### __array.join()__: 배열의 모든 요소를 쉽표나 지정된 문자열로 구분해 연결한 문자열을 반환
```js
 arr.join()
```
 기본: ,로 구분  
'': 연달아 붙임(띄어쓰기x)
## 검색

### __array.indexOf()__: 주어진 요소를 찾을 수 있는 인덱스를 반환, 찾을 수 없는 경우 -1 반환
```js
//(찾으려는 요소, 찾기 시작할 인덱스 지정)
arr.indexOf(searchElement, fromIndex)
```
```js 
 const arr = ['a', 'b', 'c' 'b'];
 consol.log(arr.indexOf('a'));  //0 리턴
 consol.log(arr.indexOf('b'));  //1 리턴
 concol.log(arr.indexOf('b', 2));    //3 리턴
 ```

 ### __array.lastIndexOf()__: 주어진 요소를 찾을 수 있는 마지막 인덱스를 반환, 찾을 수 없는 경우 -1 반환
 [__프로그래머스 0: 한 번만 등장한 문자__](https://school.programmers.co.kr/learn/courses/30/lessons/120896)  
 ```js
 arr.lastIndexOf(searchElement)
```

## __reduce()__
[코딩에브리바디](https://codingeverybody.kr/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-reduce-%ED%95%A8%EC%88%98/)

### __array.slice()__: 어떤 배열의 begin부터 end까지(혹은 end 미포함)에 대한 얕은 복사본 반환
[프로그래스 0: 잘라서 배열 저장하기](https://school.programmers.co.kr/learn/courses/30/lessons/120913)
```js
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
//["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
//["camel", "duck"]
```
