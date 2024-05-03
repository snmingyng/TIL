# 1. 이벤트 처리하기
### DOM의 이벤트
```html
<button onclick="activate()">
    Activate
</button>
```
🔼DOM에서는 클릭 이벤트를 처리할 함수를 onClick을 통해 문자열로 전달한다.
### 리액트의 이벤트
```html
<button onClick={activate}>
    Activate
</button>
```
🔼리액트에서는 이벤트를 처리할 함수를 함수 그대로 전달한다. 이벤트 이름에 카멜 표기법을 적용했다. 

> #### 🚀 카멜 표기법
> 첫 글자는 소문자로 시작하되 중간에 나오는 새로운 단어의 첫 글자를 대문자로 사용하는 표기법이다. (예시: onClick)

```jsx
function Toggle(props) {    //함수 컴포넌트생성
    //inToggleON의 초기값: true
    const [isToggleOn, setIsToggleOn] = useState(true);

    //방법 1. 함수 안에 함수로 정의
    function handleClick() {
        setIsToggleOn((isToggleOn) => !isToggleOn)
    }
    //방법 2. arrow function을 사용해 정의
    const handleClick = () => {
        setIsToggleOn((isToggleOn) => !isToggleOn);
    }
    
    return (
        <button onClick={handleClick}>
            {isTogglOn ? "켜짐" : "꺼짐"}
        </button>
    );
}
```

> ## 🚀JS의 삼항연산자
> if...else문을 대체할 수 있다.
>
> ```
> condition ? exprIfTrue : exprIfFalse;
>```
> `condition`: 조건<br>
> `exprIfTrue`: 조건이 참일 경우 실행<br>
> `exprIfFalse`: 조건이 거짓일 경우 실행

# 2. Arguments 전달하기
✅매개변수(Arguments): 함수에 전달할 데이터
```html
<button onClick={(event) => this.deleteItem(id, event)}>삭제하기</button>
```
🔼event를 두 번째 매개변수로 넣어주었다.
```html
<button onClick={this.deleteItem.bind(this.id)}>삭제하기</button>
```
🔼event가 자동으로 id 이후의 두 번째 매개변수로 전달된다.

```jsx
function MyButton(props) {
    const handleDelete = (id, event) => {
        console.log(id, event.target);
    };

    return (
        <button onClick={(event) => handleDelete(1,event)}>삭제하기</button>
    );
}
```
