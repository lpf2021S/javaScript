## 原生AJAX
### 1.1 Ajax简介
```
1. Asynchronous Javascript And XML(就是异步的 JS 和 XML)
2. 通过AJAX可以在浏览器中向服务器发送异步请求
3. 实现页面无刷新，发送请求返回数据。
4. 不是新的编程语言，而是一种将现有的标准组合在一起使用的新方式。
```

### 1.2 XML 三特点

```
1. XML是可扩展标记语言。
2. XML被设计用来传输和存储数据。
3. XML和HTML类似，不同的是HTML中都是预定义标签，而XML中没有预定义标签，全都是自定义标签，    用来表示一些数据。
```

### 1.3  XML实例

```
 <student>
        <name>孙悟空</name>
        <age>18</age>
        <gender>男</gender>
 </student>
 // JSON代替
 {  
      "name":"孙悟空",
      "age":18,
      "gender":"男"
  }
```

###  1.4 Ajax优点及缺点

1. 优点

   ```
   1. 可以无需刷新页面与服务器端进行通信
   2. 允许你根据用户事件来更新部分页面
   ```

2. 缺点

   ```
   1. 没有浏览历史，不能回退
   2. 存在跨域问题
   3. SEO不友好
   ```

### 1.5 AJAX使用

1. ```
   1.核心对象
       XMLHttpRequest,AJAX所有操作都是通过该对象进行的
   2.使用步骤
       * 创建XMLHttpRequest实例对象
            const xhr = new XMLHttpRequest()
       * 设置请求信息
            xhr.open(method,url)   // 配置请求
            xhr.setRequestHeader(key,value)  // 设置请求头
       * 发送请求
            xhr.send(body)  // body参数只有在post请求使用
       *  接受响应
            xhr.onreadystatechange = () => {
                 if(xhr.readyState===4&&xhr.status>=200&&xhr.status<300){
                     console.log(xhr.response)     
                 }
              }
   ```

2.  **解决IE缓存问题**

   ```
   1. 在一些浏览器中(IE),由于缓存机制的存在，ajax只会发送的第一次请求，剩余多次请求不会在发送给浏览器而是直接加载缓存中的数据。
   2. 浏览器的ajax缓存是根据url地址来记录的，所以我们只需要修改url地址即可避免缓存问题
   3. xhr.open('get','url/t='+Date.now())
   ```

3. **AJAX请求状态**

   ```
   xhr.readyState 可以查看请求当前的状态
   * 0: 表示XMLHttpRequest实例已经生成,但open未调用
   * 1: open已调用，但send未调用,此时仍然可以修改请求头信息
   * 2：send已调用, 此时不可修改请求头
   * 3: 小部分数据已经回来, 响应体已将返回
   * 4：所有数据已经回来。
   ```

### 2.0 跨域

1.  **同源策略**

   ```
   * 同源策略（Same-Origin Policy）由 Netscape 公司提出，是浏览器的一种安全策略。
   * 同源的规则：协议、域名、端口号 必须完全相同。
   * 违背同源策略又称：跨域。
   ```

2. **JSONP**

   ```
   1. JSONP(JSON with Padding), 非官方的跨域解决方案, 只支持get请求
   2. 在网页有一些标签天生具有跨域能力，比如：img link iframe script等。
   3. JSONP就是利用了script标签发送请求不受同源策略的限制的特点。
   4. 实现
       *  DOM创建Script标签
          const scriptNode = document.createElement('script')
       *  src属性设置为请求地址
          scriptNode.src = url
       *  通过DOM添加到页面
          document.body.appendChild(scriptNode)
       *  前端配置读取数据的函数
          window.handler =(data)=>{ 处理数据 }
       *  后端对应设置读取数据的函数调用字符串及传递数据
          response.end(`callback(${JSON.stringify(data)})`)
       *  DOM删除Script标签
          document.body.removeChild(scriptNode)
   ```

3. **CORS ( 后端技术 )**

   ```
   1. CORS（Cross-Origin Resource Sharing），跨域资源共享。CORS是官方的跨域解决方案，它的特点是不需要在客户端做任何特殊的操作，完全在服务器中进行处理，支持所有常见的请求。
   2. 在AJAX发送请求, 返回数据, 浏览器安全策略检测出跨域问题。阻止了数据的返回。 
   3. 使用方法 (设置响应头,提供特权)
      *  response.set('Access-Control-Allow-Origin',"*")
      *  response.set('Access-Control-Expose-Headers','*')
      *  response.set('Access-Control-Allow-Methods','*')
   4. PUT,DELETE 等复杂方法首先会发送一次嗅探请求。也要配置相应的响应头
      app.options(url, callback)
   ```

   ```
   //  借助cors库，应用到express中间件中
   1.  npm安装
   2.  const cors = require('cors')
   3.  app.use(cors())
   ```

   





