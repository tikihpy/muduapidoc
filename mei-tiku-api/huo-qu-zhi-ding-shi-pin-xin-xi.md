# 获取指定视频信息 {#获取指定视频信息}

#### 请求header {#请求header}

```
GET /v1/videos/{视频id}
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{视频id}"替换您需要获取的视频id`

#### 返回 {#返回}

```
{
  "id": 27379,
  "act_id": 17630,
  "name": "234.flv",
  "video_url": "http://vod.mudu.tv/example.flv",
  "video_size": 5999079,
  "m3u8": "http://vod.mudu.tv/example.m3u8",
  "m3u8_480": "http://vod.mudu.tv/example.m3u8",
  "m3u8_720": "http://vod.mudu.tv/example.m3u8",
  "m3u8_1080": "http://vod.mudu.tv/example.m3u8",
  "duration": 0,
  "width": 0,
  "height": 0,
  "cover_url": "http://cdn.mudu.tv/video_147073249442944.jpg",
  "watch_url": "http://mudu.tv/show/videolink2/27379/origin",
  "embed_url": "http://mudu.tv/show/videolink/27379/origin",
  "manager": 0,
  "upload_time": "2017-08-01 17:21:20",
  "start_time": "2017-08-01 17:21:20",
  "end_time": "2017-08-01 18:31:47"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 视频id | integer |
| act\_id | 频道id | integer |
| name | 视频名称 | string |
| video\_url | 视频原始地址 | string |
| video\_size | 视频大小\(字节\) | integer |
| m3u8 | 视频m3u8地址 | string |
| m3u8\_480 | 视频m3u8\_480地址 | string |
| m3u8\_720 | 视频m3u8\_720地址 | string |
| m3u8\_1080 | 视频m3u8\_1080地址 | string |
| duration | 视频长度\(秒\) | integer |
| width | 视频宽度 | integer |
| height | 视频高度 | integer |
| cover\_url | 视频封面地址 | string |
| watch\_url | 视频播放地址 | string |
| embed\_url | 视频嵌入地址 | string |
| manager | 频道管理员ID，视频所属非频道管理员时值为0 | integer |
| upload\_time | 视频上传时间 | datetime |
| start\_time | 视频开始时间 | datetime |
| end\_time | 视频结束时间 | datetime |



