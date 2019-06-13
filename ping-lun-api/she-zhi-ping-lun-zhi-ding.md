# 设置评论置顶 {#设置评论置顶}

#### 请求header {#请求header}

```
POST /v1/activity/{频道id}/comments/{评论id}/top
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换为您的频道id`

`请将"{评论id}"替换您需要置顶/取消置顶的评论id`

#### 请求payload {#请求payload}

```
{
    "top" : 1
}

```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 注释 |
| :--- | :--- | :--- | :--- | :--- |
| top | 设置/取消置顶 | string | 是 | 传1则为置顶，0为取消置顶 |

#### 返回 {#返回}

```
{
    "comment_id": "12345",
    "result": "success"
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| comment\_id | 被置顶的评论id | integer |
| result | 置顶标识 | string |



