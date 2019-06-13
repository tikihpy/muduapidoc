# 观众禁言 {#观众禁言}

#### 请求header {#请求header}

```
POST /v1/activity/{频道id}/comments/{观众id}/mute
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换为您的频道id`

`请将"{观众id}"替换为您想要禁言的观众visitor_id`

#### 请求payload {#请求payload}

```
{
    "mute" : 1,
    "user" : "禁言观众"
}

```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 注释 |
| :--- | :--- | :--- | :--- | :--- |
| mute | 设置/取消禁言 | string | 是 | 传1则为禁言，0为取消禁言 |
|  | user | 观众昵称 | string | 是 |

#### 返回 {#返回}

```
{
    "visitor_id": "test_visitor_id",
    "result": "success"
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| visitor\_id | 被禁言的观众visitor\_id | string |
| result | 禁言标识 | string |



