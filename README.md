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
1. Cho phép xử lý những thành phàn side effect. VD như call API, setTimeout, setInterval hay là tương tác với trình duyệt...
2. useEffect nhận đối số đầu vào là một callback
3. callback function của cả 3 trường hợp useEffect được gọi ***sau*** khi component được mount lần đầu tiên vào trong DOM
4. Có 3 trường hợp useEffect khi truyền đối số thứ hai hoặc không truyền
    1. useEffect(callback) : callback function được gọi sau khi component re-render
    2. useEffect(callback, [deps]): callback function được gọi khi ***deps*** (dependence) thay đổi 
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
3. useRef trả về một object được gọi là ***current***
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
     {console.log("re-render")}
     <button onClick={handleFocus}>Focus</button>
   </div>
 );
```

2. Lưu tham chiếu qua mỗi lần re-render

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
