# 修改频道信息 {#修改频道信息}

#### 请求header {#请求header}

```
PUT /v1/activities/{频道id}
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

```
{
    "name" : "测试频道"
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| name | 频道名称 | string | 是 |

#### 返回 {#返回}

```
{
  "id": 4133,
  "name": "修改后的测试频道",
  "create_at": "2016-08-09 10:33:51",
  "live_status": 0,
  "watch_url": {
    "pc": "http://mudu.tv/watch/80261",
    "mobile": "http://mudu.tv/?c=activity&a=live&id=4133"
  },
  "embed_url": "http://mudu.tv/?a=index&c=show&id=4133&type=mobile",
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
  "rtmp_publish_addr": "rtmp://video.mudu.tv/watch/jy1jk3",
  "hls_play_addr": "http://live.mudu.tv/watch/jy1jk3.m3u8",
  "rtmp_play_addr": "rtmp://live.mudu.tv/watch/jy1jk3"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
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



