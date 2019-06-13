# 删除评论 {#删除评论}

#### 请求header {#请求header}

```
DELETE /v1/activity/{频道id}comments/{评论id}
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{评论id}"替换您需要获取的评论id请将"{频道id}"替换您需要获取的频道id`

#### 返回 {#返回}

```
{
    "comment_id" : 12345,
    "result" : "success"
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| comment\_id | 被删除的评论id | integer |
| result | 删除标识 | string |



