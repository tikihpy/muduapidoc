# 上传视频 {#新增视频}

#### 请求header {#请求header}

```
POST /v1/videos
Authorization:Bearer {ACCESS TOKEN}
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

请使用基于[webuploader](http://fex.baidu.com/webuploader/)的插件进行开发！ server端完全按照该插件设置了分片上传的参数。 参数\(form-data格式\):

```
{
    file:文件,
    time:1501967854, // 已废弃，可以不传
    randomNum:0.793009233169936,
    chunk:0,
    chunks:30
}
```

说明:

| 字段 | 名称 | 类型 | 说明 |
| :--- | :--- | :--- | :--- |
| file | 文件 | file | 上传的视频文件 |
| time | 时间 | int | Date.parse\(new Date\(\)\)，已废弃，可以不传 |
| randomNum | 随机数 | string | Math.random\(\) |
| chunk | 当前片 | int | 0 |
| chunks | 总片数 | int | 30 |

如果不采用分片上传的话，那么一次性上传文件大小非常受限，chunk和chunks就可以不传。

上传成功返回：

```
{
    "result": "success",
    "uploadId": "on2g2vvb",
    "id": 0//分片上传过程中，此id一直为0
}
{
    "result": "success",
    "uploadId": "on2g2vvb",
    "id": 123
}

说明：

| 参数           | 描述           | 类型        |
| ------------- |:--------------:| ----------:|
| result        | 结果标识        | string     |
| uploadId      | 临时上传id      | string     |
| id            | 视频存储id      | int     |

```

上传失败返回：

```
{
    "errors": {
        "code": 错误码,
        "message": "错误消息"
    }
}

```

上传失败返回值说明：

| code | message | 备注 |
| :--- | :--- | :--- |
| 403001 | 您没有访问此资源的权限 | 请确认是否有权限 |
| 403002 | 您没有上传任何视频 | 请检查上传视频文件 |
| 403003 | 不支持此类格式文件上传！ | 请上传视频格式文件视频 |
| 500003 | Failed to move uploaded file. | 请重新上传 |
| 500004 | multipart upload init fail. | 请重新上传 |
| 500005 | part upload err. | 请重新上传 |
| 500006 | cache err. | 请重新上传 |
| 500007 | cache err cant not complete. | 请重新上传 |
| 500008 | completeMultipartUpload error. | 请重新上传 |
| 500009 | 系统内部错误 | 请重新上传 |

上传说明：

* 单个文件大小不超过10G
* 支持的文件类型为：avi,f4v,mpg,mp4,flv,wmv,mov,3gp,rmvb,mkv,asf,ts,mts,dat,vob,mp3,wav,m4v,webm,m3u8

视频文件上传流程是：文件先上传到一个临时地方，上传成功后会对文件进行转码\(从上传成功到开始转码这个过程是连续的，没有间断\)，转码成功后通过[视频转码通知](http://mudu.tv/api/v1/VIDEO_TRANSCODE.html)接口发送转码成功的通知，视频存储id也会一并返回。

