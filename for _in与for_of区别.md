##  For...of  和 for...in

#### 遍历

```
for in  索引(可迭代)/key  
for of  数组元素值(只能遍历可迭代对象)
```

#### for in

```
for(index in target)
index 为字符串
遍历自身及继承的可枚举属性(不包括symbol)
```

#### for of

```
for of适用遍历数/数组对象/字符串/map/set等拥有迭代器对象（iterator）的集合
```

