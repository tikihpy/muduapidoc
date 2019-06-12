# 上传文档 {#直播文档}

#### 请求header {#请求header}

```
POST /v1/activities/{频道id}/uploadDoc
Authorization:Bearer {ACCESS TOKEN}
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

请使用 multipart/form-data

```
Filedata ->文件字段名
```

#### 返回 {#返回}

```
{
    "status" : "y",
    "msg" : "上传成功",
    "docid" : 233
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| status | 上传结果，上传成功为"y"，失败为"n" | string |
| msg | 结果描述 | string |
| docid | 文档id，只有上传成功才会返回 | integer |

#### 主动消息推送 {#主动消息推送}

```
{
    "namespace": "doc",
    "action": "create",
    "source":"api",
    "id":23333,
    "status":1/0 //1：成功；0：失败
}

```

请在[此处](http://mudu.tv/api/v1/NOTICE_README.html)查询

