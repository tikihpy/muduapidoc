# 移动暂存视频到媒体库 {#移动暂存视频到媒体库}

#### 请求header {#请求header}

```
POST /v1/videos/move
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 请求参数 {#请求参数}

```
{
    "media_ids" : "88727,88728"
}
```

#### 请求参数说明 {#请求参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| media\_ids | 从属当前用户的合法视频id频接字符串\(使用英文逗号分割\) | string | 是 |

#### 返回 {#返回}

```
{
    "result": "success",
    "successIds": [
        "88727",
        "88728"
    ],
    "failedIds": []
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| result | 结果标识 | string |
| successIds | 成功移动的视频id | array |
| failedIds | 未成功移动的视频id | array |

失败返回：

```
{   
    errors:{
        code:'错误码',
        message:'错误信息'
    }
}
```



