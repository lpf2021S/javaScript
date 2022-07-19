## flex常用属性(6)
### 1.flex-direction
    1. row（默认值）：主轴为水平方向，起点在左端。
    2. row-reverse：主轴为水平方向，起点在右端。
    3. column：主轴为垂直方向，起点在上沿。
    4. column-reverse：主轴为垂直方向，起点在下沿。
### 2.flex-wrap
    1. nowrap（默认）：不换行。
    2. wrap ：换行，第一行在上方。
    3. wrap-reverse ：换行，第一行在下方。
### 3.flex-flow
    1. flex-flow: <flex-direction> || <flex-wrap>;
### 4.justify-content
    1. flex-start（默认值）：左对齐
    2. flex-end：右对齐
    3. center ： 居中         
    4. space-around：项目之间的间隔比项目与边框的间隔大一倍。
    5. space-between：两端对齐，项目之间的间隔都相等。
### 5.align-items
    1.flex-start：交叉轴的起点对齐。
    2.flex-end：交叉轴的终点对齐。
    3.center：交叉轴的中点对齐。
    4.baseline: 项目的第一行文字的基线对齐。
    5.stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
### 6.align-content属性
    *多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
    1.flex-start：与交叉轴的起点对齐。
    2.flex-end：与交叉轴的终点对齐。
    3.center：与交叉轴的中点对齐。
    4.space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
    5.space-around：每根轴线两侧的间隔都相等，轴线之间的间隔比轴线与边框的间隔大一倍。
    6.stretch（默认值）：轴线占满整个交叉轴。

## 项目的属性
### 1.order
* 定义项目的排列顺序。数值越小，排列越靠前，默认为0。
### 2.flex-grow
* 属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
* 如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。
### 3.flex-shrink
* 属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
* 如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。
### 4.flex-basis属性
* 默认为auto 及项目本来大小。

### 5.flex属性
```
/* 默认 */
flex-shrink:1 flex-grow:0 flex-basis:auto
/* flex : 1; */
flex-shrink:1 flex-grow:1 flex-basis:auto
```

### 6.align-self
*align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。