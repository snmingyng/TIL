# .map() 메서드
### [JS 공식문서](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map)  
### [코딩에브리바디](https://codingeverybody.kr/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-map-%ED%95%A8%EC%88%98/)

배열의 각 요소에 콜백 함수를 적용한 결과를 모아 새로운 배열을 반환한다. 원본 배열은 변경하지 않는다.
```js
const numbers = [1, 2, 3, 4, 5];

const double = numbers.map(function (n) {
    return number *2;
});
console.log(double);
//[2, 4, 6, 8, 10]  
console.log(numbers);
//[1, 2, 3, 4, 5]
```

## 화살표 함수로 표현
```js
arr.map((element) => {적용할 함수})
```

## 문제에서 활용
### [프로그래머스 0: 외계 행성의 나이](https://school.programmers.co.kr/learn/courses/30/lessons/120834)
```js
function solution(age) {
    const arrAge = String(age).split('');
    const alphabet = ['a', 'b', 'c', 'd', 'e','f','g','h','i','j'];
    
    const map1 = arrAge.map((x) => alphabet[x]);
    return map1.join('');
}
```
```js
const map1 = arrAge.map((x) => alphabet[x]);
//arrAge 배열의 x번째 요소를 alphabet 배열의 x번째 요소로 변경해 새로운 배열 생성
//각 요소마다 {새로운 배열[x] = alphabet[x]}를 적용하는 것과 같다
```



### [프로그래머스 0: 진료순서 정하기](https://school.programmers.co.kr/learn/courses/30/lessons/120835)  
```js
function solution(emergency) {
    //정렬된 새로운 배열 생성
    let levelEmerg = [...emergency].sort((a, b) => b-a);
    //입력된 배열값에 새로운 배열 인덱스+1
    return emergency.map((x) => levelEmerg.indexOf(x)+1);
}
```
```js
return emergency.map((x) => levelEmerg.indexOf(x)+1);
// emergency 배열값에 대해 (levelEmerg 배열의 인덱스값+1)을 부여한다
//[30, 10, 23, 6, 100] => [100, 30, 23, 10, 6] 적용 => [2, 4, 3, 5, 1] 리턴
//emergency[0]인 30에는 levelEmerg[1]=30의 인덱스값+1이 적용되어 {새로운 배열[0] = 2} 가 적용되었다.
```

### [프로그래머스 0: 모스부호(1)](https://school.programmers.co.kr/learn/courses/30/lessons/120838)
배열에 객체를 적용시킨 예시
### [프로그래머스 0: 가위 바위 보](https://school.programmers.co.kr/learn/courses/30/lessons/120839)
배열을 필요에 따라 만들어 적용 가능(다른 사람의 풀이 참조해서 다시 풀어볼 것)
