# React

# class3 2020/9/14

1. a
2. b
https://blog.naver.com/kiltie999/221700035599

https://velog.io/@yoopark/nomad-react-refactoring

https://blog.naver.com/ssh998/222796075738

- [ ]  todo list []

> 인용구  |
> 
- bullet lists - or *

## React JS

어플리케이션을 interactive하도록 만들어주는 library

react js 의 규칙. HTML을 html페이지에 직접 작성하지 않고 javascript 파일에 작성한다.

## ReactDOM

library or packages that allows us put all React elements in HTML body. 

react element를 html에 두는 역할. (사용자에게 보여줌)

## React.createElement()

```jsx
const btn = React.createElement(
  "button",
  {
    id: "button",
    onClick: () => console.log("clicked"),
    style: {
      backgroundColor: "tomato",
    },
  },
  "click me "
);
```

`React.createElement(html태그이름, property, content)`

event이름앞에 on을 붙이면 eventlistner인걸 react가 인지. →html에 생성 x

```jsx
const root = document.querySelector("#root");
// html에 넣을 곳. 
const container = React.createElement("div", null, [h3, btn]);
ReactDOM.render(container, root);
```

`ReactDOM.render(container, root);`  

render : 여기 React element 를 가지고 HTML로 만들어 사용자에게 보여줌. root : html에서 넣을곳

## JSX로 create element.

`<script type = "text/babel" src="reactprac.js">` 으로 html파일에 둬야 jsx 사용가능. 

```jsx
const root=document.querySelector("#root");
let counter = 0;

function countUp(){
  counter=counter+1;
  render();
  //새로 바뀐 container components를 다시 render 해줘야한다. 
  // react에서는 바뀐 부분만 보인다. 
}

// const Button = ()=>(
//     <button id="button" onClick={()=>console.log("clicked")} style ={{backgroundColor :"blue"}}>btn</button>
//     );
const Button=()=>(
  <button id="button" onClick={countUp}>Button </button>
);

function render(){
  ReactDOM.render(<Container/>, root);
}
//Container 는 함수이므로 componets로 만들어줘야된다. 

function Title() {
      return (<h3 id="title" onMouseEnter= {()=>console.log("mouseenter")}>It was clicked {counter}</h3>
                                            //{변수명} 이렇게쓰면
    );
}
    
const Container =()=> (<div><Title/><Button/></div>);
render();
```

Container에 div안에 들어가는 요소들 이름의 첫글짜는 반드시 대문자여야함. 소문자면 html 태그로 인식함. ex(<button> )
JSX로 써져있는 코드를 babel이 react.createelement 느낌의 코드로 변환 해 준다. 만든 Components를 다른데서 쓰고싶으면 함수형태로 만들고 이름 첫 글자를 대문자로 해야된다. 
 ()=> arrow function은 return까지 포함된 함수이다. 

components 나 jsx에 변수를 포함하고 싶으면 {변수명} 이렇게 html에 변수 표시.
  
ui업데이트 된거 보여주려면 `render()` 다시 호출. js에서 Total Clicks : *b5 업데이트하면 span 등 등 수정되지 않는 부분도 다 업데이트 되는데 react.js에서는 ui에서 바뀐 부분만 업데이트 됨. rerender 해도 바뀌는 부분만 업데이트됨. container가 재생성 되지만 바뀌는 숫자 부분. Total Clicks : *b4 부분만 rerender됨. 
  
-> 문제점 : 데이터 바뀔때마다 계속 다시 render() 호출해줘야됨.
  
 ## javascript 배열에서 요소들을 꺼내서 이름을 부여하는법. 
  ```
  const x=[1,2];
  const a=x[0];
  const b=x[1];
  
  const x=[1,2];
  const [a,b] = x;
  ```
  같은 표현이다. 
  
  ```function App(){
  return (
    <div>
      <h3 id = "title">It was clicked {counter}</h3>
        <button id = "button" onClick={countUp}>Click</button>
    </div>);
}
  ```
  
## Arrow function
  전통적인 함수표현의 대안. methods로 사용 불가. 생성자로 사용 불가. this 사용 불가.  
  `(param1, param2, ,,) =>{statements}` 
  ex){console.log(param1, param2,,,);}
  ```
  (param1, param2, ,,) =>expression  
  func(param1,,,,){return expression;}
  ```
  위 두 표현 같다. function이 expression계산해서 결과를 *b리턴한다. 
  ex)param1+param2; {}사용하면 안됨 return param1+param2; 를 써야 리턴가능.  
 
  
  `(singleParam)=>{statements}` or `singleParam => {statements}`
  매개변수가 하나일땐 괄호 생략가능
  `()=>{statements}`
  매개변수 없으면 괄호 필수
  `function(param1){return param1+10;}` 이랑 `const function=(param1)=>param1+10;`
  
## state, modifier 함수. 
  
   ```
  function App(){
  const [counter, setCounter] = React.useState(0);
  const onClick=()=>{
    setCounter(counter+1);
  };
  return (
    <div>
      <h3>Total clicks: {counter}</h3>
        <button onClick={onClick}>Click</button>
    </div>);
}
  ```
  `React.useState(initial value, function)`
  -> [state ,modifier] react.useState함수는 어떤값과 그 값을 바꿀 수 있는 함수modifier를 반환한다. 
  state 값 , modifier : 그 값을 바꾸는 함수.  modifier 함수 
  modifier함수로 state(counter)를 바꾸면 그 바뀐 값으로 Component전체가(App)을 재생성하고 재렌더링한다. 
  state가 바뀌면 리렌더링이 일어난다. 
  
  render()를 처음 실행하면 html에 app component 생성, 리렌더링 시 바뀐 부분만 새로 생성. 
  
  안보고 ㄱ
