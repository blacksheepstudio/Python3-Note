```js
// 调用 HTTP 模块
const http = require("http");

// 创建 HTTP 服务器并监听 8000 端口的所有请求
http.createServer((request, response) => {

   // 用 HTTP 状态码和内容类型来设定 HTTP 响应头
   response.writeHead(200, {'Content-Type': 'text/plain'});
   
   // 发送响应体 "Hello World"
   response.end('Hello World\n');
}).listen(8000);

// 在控制台打印访问服务器的 URL
console.log('服务器运行于 http://127.0.0.1:8000/');

```
### 基本知识
- 请求的一方叫客户端，响应的一方叫服务器端
- 通过请求和响应达成通信
- HTTP是一种不保存状态的协议
### 请求报文
常见的方法有：
- GET 获取资源
- POST 向服务器端发送数据，传输实体主体
- PUT 传输文件
- HEAD 获取报文首部
- DELETE 删除文件
- OPTIONS 询问支持的方法
- TRACE 追踪路径
- 响应报文
|column1|column2|column3|
|-|-|-|
|content1|content2|content3|


