# 获取视频列表 {#获取视频列表}

#### 请求header {#请求header}

```
GET /v1/videos
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 可选参数 {#可选参数}

`title=视频名称&act_id=视频所属频道id&manager=频道管理员ID&perPage=每页显示条数&p=页码`

#### 可选参数说明 {#可选参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| title | 视频名称，支持模糊查询 | string |
| act\_id | 视频所属频道id | integer |
| manager | 频道管理员ID | integer |
| perPage | 每页显示条数，默认10条 | integer |
| p | 页码，默认第一页 | integer |

#### 返回 {#返回}

```
{
  "videos": [
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
      "end_time": "2017-08-01 18:31:47",
      "is_bookmarked": 1,
      "bookmarks": [
        {
          "time" : "00:00:03",
          "desc" : "打点描述"
        }
      ]
    }
  ],
  "meta": {
    "total": 1,
    "page": 1,
    "current": 1,
    "auto_save_live_video": false
  },
  "links": {
    "next_url": null,
    "end_url": "http://api.mudu.tv/v1/videos?&p=1&act_id=17630&perPage=10"
  }
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| videos | 视频列表\(每页10个\) | json array |
| meta | 视频列表其他信息 | json array |
| links | 视频列表信息 | json array |
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
| is\_bookmarked | 是否是打点视频 | integer |
| total | 视频总个数 | integer |
| page | 视频总页数 | integer |
| current | 当前视频页数 | integer |
| auto\_save\_live\_video | 是否自动移到媒体库 | boolean |
| next\_url | 下一页地址 | string |
| end\_url | 最后一页地址 | string |
| bookmarks | 打点信息 | json array |
| time | 打点时间 | string |
| desc | 打点描述 | string |



