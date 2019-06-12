# 获得频道列表 {#获得频道列表}

#### 请求header {#请求header}

```
GET /v1/activities
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 可选参数 {#可选参数}

`live=直播状态&manager=频道管理员ID&p=页码`

#### 可选参数说明 {#可选参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| live | 直播状态，1为正在直播 | integer |
| manager | 频道管理员ID | integer |
| p | 页码（每页30条数据） | integer |

#### 返回 {#返回}

```
{
  "activities": [
    {
      "id": 1928,
      "name": "测试",
      "create_at": "2016-01-06 16:42:26",
      "live_status": 0,
      "watch_url": {
        "pc": "http://mudu.tv/watch/42776",
        "mobile": "http://mudu.tv/?c=activity&a=live&id=1928"
      },
      "embed_url": "http://mudu.tv/?a=index&c=show&id=1928&type=mobile",
      "page": {
        "start_time": "",
        "logo": "http://cdn13.mudu.tv/assets/upload/146467764819385.png",
        "pc_logo": "http://cdn13.mudu.tv/assets/upload/146467764819385.png",
        "mobile_logo": "http://cdn13.mudu.tv/assets/upload/146467764819385.png",
        "banner": "http://mudu.tv/assets/img/activity/pc/banner.jpg",
        "cover_image": "http://mudu.tv/assets/img/activity/pc/logo.png",
        "live_img": "http://mudu.tv/assets/console/images/livecoverimg.jpg",
        "footer": "技术支持：目睹直播技术开发团队"
      },
      "rtmp_publish_addr": "rtmp://video.mudu.tv/mudu_dev/dfads6",
      "hls_play_addr": "http://live.mudu.tv/watch/dfads6.m3u8",
      "rtmp_play_addr": "rtmp://live.mudu.tv/watch/dfads6",
      "manager": 1,
      "manager_username": "频道管理员A",
      "last_push_stream_at": "2016-11-11 14:48:54",
    }
  ],
  "meta": {
        "total": 1,
        "page": 1,
        "current": 1
  },
   "links": {
       "next_url": null,
       "end_url": "http://api.mudu.com/v1/activities?&p=1"
   }
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| activities | 所有频道信息 | json array |
| meta | 额外信息 | json array |
| id | 频道id | integer |
| name | 频道名称 | string |
| create\_at | 创建时间 | datetime |
| live\_status | 直播状态\(0为没有直播,1为正在直播\) | integer |
| watch\_url | 直播观看地址 | json array |
| pc | PC端观看地址 | string |
| mobile | 手机端观看地址 | string |
| embed\_url | 直播嵌入地址 | string |
| page | 直播页面数据 | json array |
| start\_time | 直播开始时间 | datetime |
| logo | 此字段不再使用，值是pc\_logo | string |
| pc\_logo | PC端视频LOGO地址 | string |
| mobile\_logo | 移动端视频LOGO地址 | string |
| banner | banner地址 | string |
| cover\_image | 频道图标地址 | string |
| live\_img | 直播窗口背景地址 | string |
| footer | 底部版权信息 | string |
| rtmp\_publish\_addr | RTMP发布地址 | string |
| hls\_play\_addr | hls播放地址\(仅流量版用户有该字段\) | string |
| rtmp\_play\_addr | rtmp播放地址\(仅流量版用户有该字段\) | string |
| manager | 频道管理员ID，非频道管理员创建的频道值为0 | integer |
| manager\_username | 频道管理员用户名， 非频道管理员创建的频道值为空 | string |
| last\_push\_stream\_at | 最后推流时间 | datetime |
| total | 频道总数量 | integer |
| page | 总页数 | integer |
| current | 当前页 | integer |
| next\_url | 下一页链接 | string |
| end\_url | 最后一页链接 | string |



