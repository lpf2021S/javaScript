## spread 扩展运算符

### 展开数组

```js
let tfboys = ['恋色空','深爱','命运之声']
function fn(...arg){
    console.log(arg)    // 一个数组，原型指向Array
    console.log(arguments) //一个对象，
}
fn(...tfboys)  // fn('恋色空','深爱','命运之声')

```

### 展开对象

```js
let skill = {
     applySkill:function(){
         console.log(this.name)
     }
}
let skillName = {
     name:'弹幕能量'
}
let it = {...skill,...skillName}
```

