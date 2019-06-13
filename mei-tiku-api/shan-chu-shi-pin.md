# 删除视频 {#删除视频}

#### 请求header {#请求header}

```
DELETE /v1/videos/{视频id}
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{视频id}"替换您需要获取的视频id`

#### 返回 {#返回}

```
{
  "result": "success"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| result | 删除标识 | string |



