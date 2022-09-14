# React

# class3 2020/9/14

1. a
2. b

click [https://yopark.notion.site/React-ReactJS-23ab50b8bcfc42c788750844726f3d06](https://www.notion.so/React-ReactJS-23ab50b8bcfc42c788750844726f3d06)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e66423c0-3162-4e65-864d-bdf00582d4cc/Untitled.png)

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

{변수명} 이렇게 html에 변수 표시.
