# 获取评论数 {#获取评论数}

#### 请求header {#请求header}

```
GET /v1/activity/{频道id}/comments/count
Authorization:Bearer {ACCESS TOKEN}

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 返回 {#返回}

```
{
    "count": 100
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| count | 数目 | integer |  |



