# 发布官方评论 {#发布官方评论}

#### 请求header {#请求header}

```
POST /v1/activity/{频道id}/official
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

```
{
    "username" : "测试观众",
    "message" : "测试评论",
    "title" : "官方",
    "avatar" : "http://mudu.tv/assets/avatar.png"
}

```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 注释 |
| :--- | :--- | :--- | :--- | :--- |
| username | 观众昵称 | string | 是 |  |
| message | 评论正文 | string | 是 |  |
| title | 观众头衔 | string | 否 | 默认为："官方" |
| avatar | 观众头像 | string | 否 | 不传此参数会分配一个默认头像 |



