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
## 基本知识
- 请求的一方叫客户端，响应的一方叫服务器端
- 通过请求和响应达成通信
- HTTP是一种不保存状态的协议
## 请求报文
常见的方法有：
- GET 获取资源
- POST 向服务器端发送数据，传输实体主体
- PUT 传输文件
- HEAD 获取报文首部
- DELETE 删除文件
- OPTIONS 询问支持的方法
- TRACE 追踪路径
- 响应报文

## 响应报文
### 状态码
|类别|说明|
|-|-|
|1XX|Informational(信息性状态码|
|2XX|Success(成功状态码)|
|3XX|Redirection(重定向)|
|4XX|Client Error(客户端错误状态码)|
|5XX|Server Error(服务器错误状态吗)|

### 2XX 成功
200(OK 客户端发过来的数据被正常处理
204(Not Content 正常响应，没有实体
206(Partial Content 范围请求，返回部分数据，响应报文中由Content-Range指定实体内容
### 3XX 重定向
301(Moved Permanently) 永久重定向
302(Found) 临时重定向，规范要求方法名不变，但是都会改变
303(See Other) 和302类似，但必须用GET方法
304(Not Modified) 状态未改变 配合(If-Match、If-- Modified-Since、If-None_Match、If-Range、If-Unmodified-Since)
307(Temporary Redirect) 临时重定向，不该改变请求方法
### 4XX 客户端错误
400(Bad Request) 请求报文语法错误
401 (unauthorized) 需要认证
403(Forbidden) 服务器拒绝访问对应的资源
404(Not Found) 服务器上无法找到资源
### 5XX 服务器端错误
500(Internal Server Error)服务器故障
503(Service Unavailable) 服务器处于超负载或正在停机维护
