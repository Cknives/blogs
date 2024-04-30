curl常见用法：
1）只打印返回状态码：curl -sIL -w "%{http_code}\n" -o /dev/null http://127.0.0.1:8080
