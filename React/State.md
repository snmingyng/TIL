# 1. State란
✅ **state: 리액트 컴포넌트의 변경 가능한 데이터.** <br>
렌더링이나 데이터 흐름에 사용되는 값만 state에 포함시켜야한다.
## (1) State의 특징
리액트의 state는 그냥 하나의 JS 객체다. 
```jsx
class LikeButton extends React.Component {
    constructor(props) { //생성자, 클래스가 생성될때 실행되는 함수
        super.(props);
        this.state = {
            liked: false
        };
    }
    ...
}
```
```jsx
this.state = {
    name: "Inje"
};
```
🔼(잘못된 사용법)state를 직접 수정하면 안된다.
```js
this.setState = ({
    name: "Inje"
});
```
🔼(올바른 사용법) **setState** 함수를 사용해 수정해아한다.

# 2. 생명주기에 대해
컴포넌트가 생성되는 시점과 사라지는 시점이 정해져 있다. 

출생(Mounting)-인생(Updating)-사망(Unmounting)

+ 마운트(출생): 컴포넌트의 constructor(생성자)실행, 생성자에서는 컴포넌트의 state를 정의한다. 컴포넌트가 렌더링 되고 이어서componentDidMount() 함수가 호출된다. 
+ 업데이트(인생): 컴포넌트의 props가 변경되거나 setState()함수 호출에 의해 state가 변경되거나 컴포넌트 재렌더링된다. 그 후 componentDidUpdate() 함수가 호출된다. 
+ 언마운트(사망): 상위 컴포넌트에서 현재 컴포넌트를 더이상 화면에 표시하지 않게 될 때 언마운트되며 componentWillUnmnount()함수가 호출된다.

클래스 컴포넌트에서는 생명주기 함수를 직접 사용할 수 있다.
+ componantDidMount()
+ componantDidUpdate()
+ componantWillUnmaount()


