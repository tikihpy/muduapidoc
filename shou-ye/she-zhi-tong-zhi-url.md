# 设置通知URL {#设置通知url}

_**假设设置的通知URL是**_**`http://www.foo.com/ ，`**_**那么每次调用主动推送消息的API的时候，会通过POST方式向该地址主动发送json Data。**_

#### 请求header {#请求header}

```
POST /v1/notify
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 请求payload {#请求payload}

```
{
    "url":"http://www.foo.com/"
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| url | 发送通知的URL | string | 是 |

#### 返回 {#返回}

```
{
    "result":"success"
}
```



