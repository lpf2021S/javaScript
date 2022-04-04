## rest 参数

### 简介

1. ES6引入rest参数，用于获取函数的实参，用来代替arguments

2. ```js
   //  作用与arguments相同
   function f(...args){
       console.log(args);
   }
   // 必须是最后一个参数
   function g(a,b,...args){
      console.log(args);   //是一个数组，不包括a,b
      console.log(arguments);//是一个对象，所有参数
   }
   ```

   

