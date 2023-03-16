# React-hook

## #useState

1. useState nhận đối số thứ nhất là giá trị khởi tạo cho state.
2. Fuction component sẽ được re-render mỗi khi setState được gọi.

### Usage

```reactjs
 import { useState } from "react";

 const [state, setState] = useState(inititalValue)
```

#### Example

[Example](https://codesandbox.io/s/react-hook-ebsj1l?file=/src/App.js) in codesandbox

```reactjs
 const [count, setCount] = useState(0);

 const handleAdd = () => {
   setCount(count + 1);
 };

 return (
   <div className="App">
     <h1>{count}</h1>
     <button onClick={handleAdd}>Add</button>
   </div>
 );
```

## #useEffect

1. Cho phép xử lý những thành phần side effect. VD như call API, setTimeout, setInterval hay là tương tác với trình duyệt...
2. useEffect nhận đối số đầu vào là một callback
3. callback function của cả 3 trường hợp useEffect được gọi **_sau_** khi component được mount lần đầu tiên vào trong DOM
4. Có 3 trường hợp useEffect khi truyền đối số thứ hai hoặc không truyền
   1. useEffect(callback) : callback function được gọi sau khi component re-render
   2. useEffect(callback, [deps]): callback function được gọi khi **_deps_** (dependence) thay đổi
   3. useEffect(callback, []): chỉ được gọi lúc component mount lần đầu tiên

### Usage

```reactjs
 import { useEffect } from "react";

 useEffect(() => {
  // code here
 })
```

#### Example

[useEffect example](https://codesandbox.io/s/useeffect-ks2bxr) in codesandbox

## #useRef

1. Được dùng để lưu tham chiếu qua mỗi lần re-render
2. Truy cập trực tiếp vào DOM element
3. useRef trả về một object được gọi là **_current_**

### Usage

```reactjs
  import { useRef } from "react";

  const refElement = useRef();
```

#### Example

1. Truy cập trực tiếp vào DOM element

[useRef truy cập vào DOM element example](https://codesandbox.io/s/useref-xcmzbd?file=/src/App.js) in codesandbox

```
 const inputElement = useRef();

 const handleFocus = () => {
   inputElement && inputElement.current.focus();
 };
 return (
   <div className="App">
     <input type="text" placeholder="add something" ref={inputElement} />
     <button onClick={handleFocus}>Focus</button>
   </div>
 );
```

2. Lưu tham chiếu qua mỗi lần re-render (Đồng hồ đếm ngược bắt đầu và dừng lại)

[useRef example](https://codesandbox.io/s/useref-re-render-7ic9xb?file=/src/App.js)

```
 const [count, setCount] = useState(60);

 const timerID = useRef();

 const handleStart = () => {

   timerID.current = setInterval(() => {
     setCount((prev) => prev - 1);
   }, 1000);

   console.log(timerID.current);

 };

 const handleStop = () => {
   console.log(timerID.current);

   clearInterval(timerID.current);
 };

 return (
   <div className="App">
     <h1>{count}</h1>
     <button onClick={handleStart}>Start</button>
     <button onClick={handleStop}>Stop</button>
   </div>
 );
```

## ReactJS vs Javascript

1. What is features of ReactJS ?

- JSX (Javascript + XML) : Cú pháp mở rộng của Javascript
- Component: tạo ra các khối trong app
- Virtual DOM : DOM ảo cũng giống như DOM thật, khi state or props thay đổi thì so sánh với DOM ảo và chỉ cập nhật thành phần thay đổi trên DOM thật (Lưu trong memory)
- One-way-data-binding
- High Performance: Only update component change instead all at once in app

2. Can web browser read directly JSX ? (Cannot read directly)

- Transformed into regular Javascript Object using Babel

3. ES5 vs ES6

- Require vs Import
- Exports vs Export
- Class and Function component

4. Arrow function is short way of writing function in React ( Arrow function dont have bind ‘this’ )

5. What is state in React?

- Là built in React Object chứa trạng thái hoặc thông tin của component
- When state change, component re-render (using setState)

6. What is props in React?

- Props : React built in object (properties) chứa giá trị thuộc tính của tag và hoạt động tương tự như HTML attribute
- Props cung cấp cách để pass value đến component khác

7. What difference State and Props ?

- Props không thể thay đổi ( state có thể thay đổi khi dùng useState )
- Props is read only ( state changes is asynchronous )

8. Life Cycle

- Part 1: The creation
  - Constructor
  - Render
  - ComponentDidMount ( when component mount in first time, React will call ComponentDidMount() )
- Part 2: Update Component
  - ComponentWillUpdate()
  - ComponentDidUpdate()
- Part 3: Component Unmounting
  - ComponentWillUnmount()

9. Two way binding (React is one way binding)

- The data change in a view has updated the state
- The data in state updated has updated the view

10.

- Async : make function return a promise
- Await : make function wait for a promise

11. Closure function
12. Pure function
13. How many type of constructor ?

- default: dont have parameter
- parameted
- copy constructor (it gap)

14. Interface

- La mot kieu
- Giong voi class, nhung interface khong implement cac phuong thuc (khong co phan noi dung)
- Khong co constuctor va cung khong co destructor
- Dung de dinh nghia mot khuon mau hoac quy tac chung

15. Hoisting : move declarations to the top of current scope

- JS only hoists declaration, not initialization \*

```
  // let : result is Reference Error
  carName = 'Volvo'
  let carName;

  // const : this code will not run
  carName = 'Volvo'
  const carName;
```

## CSS

1.  Block element vs Inline element

- Block element : div , p, li, table, ...
- Inline element: span, a , img, input, button
