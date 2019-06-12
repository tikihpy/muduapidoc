# 设置自定义授权跳转地址 {#设置自定义授权跳转地址}

#### 请求header {#请求header}

```
POST /v1/activities/{频道id}/setAuthUrl
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

```
{
    "redirect_url" : "http://your-website-url"
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| redirect\_url | 自定义授权跳转地址 | string | 是 |

#### 返回 {#返回}

```
{
  "status": "y",
  "msg": "设置成功"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| status | 设置结果 | string | y为成功，n为失败 |
| msg | 结果描述 | string |  |



