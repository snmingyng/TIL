# 1. 리액트 엘리먼트에 대해
리액트 엘리먼트 ➡️ 리액트 앱의 가장 작은 블록들, 자바스크립트 객체 형태로 존재.

# 2. 엘리먼트의 생김새
리액트 엘리먼트는 컴포넌트 유형과 속성 및 내부의 모든 자식에 대한 정보를 포함하고있는 JS 객체다. (불변성 포함: 한번 생성되면 바꿀 수 없다.)

```jsx
fuction Button(props) {
    return (
        <button className={`bg-${props.color}`}>
            <b>
                {props.children}
            </b>
        </button>
    )
}

fuction ConfirmDialog(props) {
    return (
        <div>
            <p>내용을 확인하셨으면 확인 버튼을 눌러주세요. </p>
            //Button 컴포넌트를 포함
            <Button color='green'>확인</Button>
        </div>
    )
}
```

# 3. 엘리먼트의 특징
**불변성**: 변하지 않는 성질. ➡️ 엘리먼트 생성 후에는 children이나 attributes를 변경할 수 없다.

>#### 🚀 붕어빵 예시: 객체지향 프로그래밍에서 배운 클래스와 비슷한 개념인듯 하다. 
>컴포넌트: 붕어빵 틀<br>
붕어빵 제조 과정: 엘리먼트 생성 <br>
엘리먼트: 완성된 붕어빵(이미 구워진 붕어빵 안에 들어있는 소를 바꿀 수 없다.)

변경된 엘리먼트를 화면에 보여주기 위해서는? **➡️새로운 엘리먼트를 만들어서 기존 엘리먼트와 바꿔치기한다.**

화면이 갱신되는 횟수도 실제 리액트를 이용할 때 성능에 큰 영향을 미친다.

# 4. 엘리먼트 렌더링하기
```jsx
const element = <h1>안녕, 리액트!</h1> //엘리먼트 생성
//ReactDOM의 createRoot()함수를 사용해 만든 root
const root = ReactDOM.createRoot(document.getElementById('root'));
//root의 render() 함수 사용.
root.render(element);
```

# 4. 렌더링된 엘리먼트 업데이트
```jsx
function Clock(props) {
    return(
        <div>
            <h1>안녕, 리액트!</h1>
            <h2>현재 시간: {new Date().toLocaleTimeString()}</h2>
        </div>
    );
}
```
콘솔을 열어 확인하면 매 초 변경되는 부분이 깜빡인다

>✅**리액트에서는 엘리먼트의 불변성 때문에 변경되는 부분에 새로운 엘리먼트를 만들어서 기본 엘리먼트와 바꿔서 변경점을 보여준다.**