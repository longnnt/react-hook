# React-hook

## #useState
Cho phép thêm trạng thái vào một function component

### Usage

```reactjs
 import { useState } from "react";
```

#### Example

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
1. useState nhận đối số thứ nhất là giá trị khởi tạo cho state. Trong trường hợp này biến count được khởi tạo bằng 0
2. Fuction component sẽ được re-render mỗi khi setState được gọi. Trong trường hợp này là setCount
