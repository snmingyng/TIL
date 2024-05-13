# 1. 조건부 렌더링이란
Conditiononal Rendering: 어떠한 조건에 따라서 렌더링이 달라지는 것.

```jsx
function UserGreeting(props){
    ...
}
function GuestGreeting(props){
    ...
}

function Greeting(props) {
    const isLoggedIn = props.isLoggedIn;
    if (isLoggedIn) {   //IsLoggedIn이 true일 떄 UserGreeting 컴포넌트 리턴
        return <UserGreeting />;
    }
    return <GuestGreeting />;
}
```

# 2. 엘리먼트 변수
렌더링해야 할 컴포넌트를 변수처럼 다루고싶을 때 사용하는 방법니다.
```jsx
function LoginButton(props){
    ...
}
function LogoutButton(props){
    ...
}

function LoginControl(props) {  //로그인 상태 저장
    const [isLoggedIn, setIsLoggedIn]= useState(false);

    const handleLoginClick = () => {
        setLoggedIn(true);
    }
    const handleLogoutClick = () => {
        setLoggedIn(false);
    }

    let button;
    //isLoggedIn의 값에 따라 button이라는 변수에 컴포넌트를 대입한다.
    if (isLoggedIn) {
        button = <LogoutButton onClick{handleLoggoutClick} />;
    } else {
        button = <LoginButton onClick{handleLoggintClick} />;
    }

    return (    //컴포넌트가 대입된 button을 return에 넣어 실제 컴포넌트(리엑트 엘리먼트) 렌더링
        <div>
        <Greeting isLoggedIn={inLoggedIn} />
        {button}
        </div>
    )
}
```
🔼button 변수에 컴포넌트를 대입했다. 그리고 return에 넣어 컴포넌트로부터 생성된 리액트 엘리먼트가 렌더링 되도록 한다.

# 3. 인라인 조건