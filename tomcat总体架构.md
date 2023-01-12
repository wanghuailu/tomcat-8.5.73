1. Server：
    1) 监听端口，接受请求，并做处理，返回结果
    2) start() 打开socket链接，监听服务器端口，接受到客户端请求时进行处理并返回响应
    3) stop() 关闭服务，释放网络资源

2. Connector 和 Container
    1) Connector 开启socket并监听客户端请求，返回响应数据
    2) Container 负责具体的请求处理
    3) Service 负责维护多个 Connector 和 一个 Engine（相当于是 Servlet 引擎）

3. Context