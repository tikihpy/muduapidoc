# API使用指南 {#api使用指南}

### API介绍 {#api介绍}

#### 简介 {#简介}

目睹API提供灵活的资源控制方式，满足您的定制化需求。

目睹API需要使用 ACCESS TOKEN 发起API请求。

#### API使用步骤 {#api使用步骤}

API的使用分为三步：

1.成为专业版用户，点此[升级为专业版](http://mudu.tv/console/?c=bill&a=upgrade)

2.得到ACCESS TOKEN：点此[获取ACCESS TOKEN](http://mudu.tv/console/?c=account&a=apisetting)。

3.使用第二步中得到的ACCESS TOKEN，便可以访问目睹API中的全部接口服务，如果请求没有带上ACCESS TOKEN，目睹API的安全机制将会视其为未授权访问操作，并将其拦截。

#### API域名 {#api域名}

`http://api.mudu.tv`

#### API错误响应 {#api错误响应}

错误响应消息

```
{
 "errors":{
   "code":错误码,
   "message":"状态描述"
  }
}
```

错误码对照表

400 Bad Request

```
400001 Invalid parameters
400002 Missing parameters
```

401 Unauthorized

```
401001 Unauthorized user
```

403 Forbidden

```
403001 Not allowed to access
403002 Permission not allowed
```

404 Not Found

```
404001 No such user
404002 No such activity
404003 No such video
```

405 Method Not Allowed

```
405001 Http method not allowed
```

429 Too Many Requests

```
429001 Touch rate limit
```

500 Internal Server Error

```
500001 Server logic error
500002 Internal server error
```
