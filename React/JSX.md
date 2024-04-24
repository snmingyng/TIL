# 1. JSX란?
Javascript+XML/HTML


```jsx
const element = <h1>Hello, World</h1>
```

const: 자료형<br>
element: 변수명 <br>
h1태그로 둘러싸인 문자열을 element라는 변수에 저장.

➡️변수에 HTML 문법을 저장하는 것으로 봐도 무방해보인다.


# 2. JSX의 역할
JSX는 XML/HTML 코드를 JS로 변환하는 역할을 한다.

리액트에서는 `createElement()` 함수가 이 역할을 한다.

```jsx
class Hello extends React.Componant{
    render() { //React.createElement 사용
        return React.createElement('div', null, `Hello ${this.props.toWhat}`);
    }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root. render(React.createElement(Hello, {toWhat: 'World'}, null));
```
🔼JSX를 사용하지 않고 JS만을 사용

```jsx
class Hello extends React.Componant{//Hello라는 이름을 가진 리액트 컴포넌트
    render() {
        //React.createElement 사용했던 부분을 JSX로 대체
        return <div>Hello {this.props.toWhat}</div>;
    }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root. render(<Hello toWhat="World" />);
// Hello를 렌더(World를 this.props.toWhat에 적용?=Hello World 출력)
```
🔼JSX를 사용해 간결해진 코드.

JSX를 사용하면 리액트 내부에서 createElement 함수를 사용한 것으로 변환한다.
```jsx
const element = (
    <h1 className="gleeting">
    Hello, world!
    </h1>
)
//동일한 역할을 하는 js 코드
const element = React.createElement(
    'h1',
    {className: 'gleeting' },
    'Hello, world!'
)
```

# 3. JSX 사용법

```jsx
funtion formatName(user){   //JS 함수 정의
    return user.firstName + ' ' + user.lastName;
}

const user = {
    firstName: 'Inje'
    lastName: 'Lee'
};

const element = (
    <h1>
        Hello, {formatName(user)} //formatName JS함수 호출
    </h1>
);

const root = ReactDoM.createRoot(document.getElementById('root'));
root.render(element);
```
✅ **JSX에서 중괄호를 사용하면 무조건 JS 코드가 들어간다**
