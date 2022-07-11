# React-hook

## #useState
Cho phép thêm trạng thái vào một function component

### Usage

```reactjs
 import { useState } from "react";
```

#### Example
[Example]([https://duckduckgo.com](https://codesandbox.io/s/react-hook-ebsj1l?file=/src/App.js))

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
***1.*** useState nhận đối số thứ nhất là giá trị khởi tạo cho state. Trong trường hợp này biến count được khởi tạo bằng 0
***2.*** Fuction component sẽ được re-render mỗi khi setState được gọi. Trong trường hợp này là setCount

## #useEffect
Cho phép xử lý những thành phàn side effect. VD như call API, setTimeout, setInterval hay là tương tác với trình duyệt...

### Usage

```reactjs
 import { useEffect } from "react";
```
***1.*** useEffect nhận đối số đầu vào là một callback
