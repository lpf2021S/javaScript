## Grid

### Attribute (属性)

#### 1. 开启grid布局

```css
display : grid;
```

#### 2. row / column

```css
/* 设置行(row)、列(column)的数量和大小 */
/* 单位为 px % fr */
/* 行(row)的长度以最大单位为准 */
grid-template-columns: 1fr 200px;
grid-template-rows: 1fr 1fr;
```

#### 3. gap

```css
column-gap:10px;
row-gap:40px;
```

#### 4.对齐

```
/* grid方块内元素对齐 默认元素拉伸*/ 
align-items:center;
justify-items:center;

/* grid元素对齐*/
justify-items: center;
align-items: center; 
```

#### 5.指定行(row)、列(column)

```
grid-row: 1 / -1 ;
grid-column: 1 / 3;
grid-column: 1 / span 3;
```

