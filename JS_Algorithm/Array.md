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
