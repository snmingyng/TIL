# 1. 컴포넌트에 대해
리액트 컴포넌트에 있어서 <br>
입력: **props** <br>
출력: 리액트 엘리먼트

✅**리액트 컴포넌트는 어떠한 속성들(props)을 입력받아서 그에 맞는 리액트 엘리먼트를 생성해 리턴해준다.**
> #### 🚀붕어빵 예시: 객체지향과 비슷한 개념을 갖고 있는 것이 맞다. (붕어빵 틀만 있으면 재료를 넣어 계속 붕어빵 생성 가능) 
> 컴포넌트=붕어빵 틀 props=붕어빵 재료 엘리먼트=완성된 붕어빵

# 2. Props에 대해
## (1) props=property : 속성, 특성

✅**props는 컴포넌트에 전달할 다양한 정보를 담고 있는 JS 객체다.**

## (2) props의 특징
✅ **읽기 전용(값을 변경할 수 없다.)**
> ### JS함수의 속성
>```js
>//input을 변경하지 않으며 input에 대해서 항상 같은 output을 리턴
>fution sum(a, b) {
>    return a+b;
>}
>```
>✅Pure하다: 입력값을 변경하지 않으며, 같은 입력값에 대해서는 항상 같은 값을 출력한다는 뜻
>```js
> //입력으로 받은 account의 값을 변경했다.
> function withdraw(account, amount) {
>    account.total -= amount;
>}
>```
>✅Impure하다: 입력으로 받은 값을 변경한다.

✅모든 리액트 컴포넌트는 props에 대해서 Pure함수같은 역할을 해야한다 ➡️ **모든 리액트 컴포넌트는 props를 직접 바꿀 수 없고, 같은 props에 대해서는 항상 같은 결과를 보여야한다!**

# 3. 컴포넌트 만들기
## (1) 컴포넌트의 종류
+ 컴포넌트
  * 함수 컴포넌트 (현재 많이 사용한다.)
  * 클래스 컴포넌트 (리액트 초기 버전에서 사용)
  
## (2) 함수 컴포넌트
```jsx
function Welcome (props) {
    return <h1>안녕, 리액트!</h1>;
}
```
🔼하나의 props 객체를 받아서 인사말이 담긴 리액트 엘리먼트를 리턴한다. 

## (3) 클래스 컴포넌트
```jsx
class Welcome extends React.Componant {
    render() {
        return <h1>안녕, (this.props.name)</h1>;
    }
}
```
🔼함수 컴포넌트의 예시와 같은 역할을 하는 컴포넌트를 클래스 형태로 만든 것. 리액트의 모든 클래스 컴포넌트는 React.Component를 상속받아서 만든다. (🚀객체지향)

## (4) 컴포넌트 이름 짓기
✅**컴포넌트의 이름은 항상 대문자로 시작해야 한다.**<br>
소문자로 시작하는 컴포넌트는 리액트가 DOM 태그(div, span 등...)로 인식하기 때문이다.
```jsx
// HTML div 태그로 인식하는 경우
const element = <div />;

//Welcom이라는 리액트 컴포넌트로 인식하는 경우
//만약 소문자 welcome으로 쓴다면 리액트가 DOM태그라고 인식해 오류가 발생한다.
const element = <Welcome name="인제" />;
```
## (5) 컴포넌트 렌더링하기
```jsx
//함수 컴포넌트 선언
function Welcome(props) {
    return <h1> Hi, {props.name} </h1>;
} 
//엘리먼트 생성
const element = <Welcome name="인제" />;
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(element); 
```
# 4. 컴포넌트 합성
여러 개의 컴포넌트를 합쳐서 하나의 컴포넌트를 만들 수 있다.
```jsx
function Welcome(props) {
    return <h1> Hi, {props.name} </h1>;
} 

function App(props) {
    return {
        <div>
            <Welcome name ="Mike" />
            <Welcome name ="Steve" />
            <Welcome name ="Jane" />
        </div>
    }
} 

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />); 
```
🔼App이라는 컴포넌트는 props 값을 다르게 한 Welcome 컴포넌트 세 개를 포함한 컴포넌트가 된다.
# 5. 컴포넌트 추출
큰 컴포넌트에서 일부를 추출해 새로운 컴포넌트를 만들 수 있다.