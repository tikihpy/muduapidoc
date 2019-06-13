# 视频转码通知 {#视频转码通知}

```
POST notify_url
Content-Type:application/json

```

参数：

```
{
    "namespace": "video",
    "action": "transcode",
    "temp_id": 123,
    "id": 123
}

```

参数说明：

| 字段 | 名称 | 类型 |
| :--- | :--- | :--- |
| namespace | 接口类型 | string |
| action | 接口动作 | string |
| temp\_id | 临时id\(已废弃，返回值同id\) | integer |
| id | 视频id | integer |

注意： 视频转码成功后，会主动向notify\_url发送通知，所以请先参考[通知API](http://mudu.tv/api/v1/NOTICE_README.html)设置通知URL！

