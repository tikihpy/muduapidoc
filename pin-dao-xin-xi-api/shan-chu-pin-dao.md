# 删除频道 {#删除频道}

#### 请求header {#请求header}

```
DELETE /v1/activities/{频道id}
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 返回 {#返回}

```
{
    "id": 4133,
    "result": "success"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 被删除的频道id | integer |
| result | 删除标识 | string |



