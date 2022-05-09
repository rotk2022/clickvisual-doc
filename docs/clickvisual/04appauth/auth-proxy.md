# Auth Proxy

你可以将 Mogo 配置为让 HTTP 反向代理处理身份验证，通过这种方式你可以很方便的将 Mogo 嵌入到其他系统里。下面我们详细介绍 auth proxy 的配置选项。



HTTP Proxy 配置：
```
[auth.proxy]
# Defaults to false, but set to true to enable this feature
enabled = true
# HTTP Header name that will contain the username or email
headerName = "X-WEBAUTH-USER"
```

使用 Curl 测试 Mogo 的 AuthProxy 功能：
```
curl -H "X-WEBAUTH-USER: shimo"  http://localhost:19001/api/v1/users/info
[
{
"id":1,
"name":"shimo",
"login":"shimo",
"email":"shimo@shimo.im",
"isAdmin":true
}
]
```

第三方系统通过 AuthProxy 嵌入Mogo：

![img.png](../../images/auth-proxy.png)image.png