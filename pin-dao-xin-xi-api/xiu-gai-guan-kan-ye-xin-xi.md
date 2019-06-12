# 修改频道页面信息 {#修改频道页面信息}

#### 请求header {#请求header}

```
PUT /v1/activities/{频道id}/page
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

```
{
    "start_time" : "2016-09-10 08:00:00",
    "pc_logo" : "http://xxx.com/logo.png",
    "mobile_logo" : "http://xxx.com/logo.png",
    "banner" : "http://xxx.com/banner.png",
    "cover_image" : "http://xxx.com/cover.png",
    "live_img" : "http://xxx.com/live.png",
    "footer" : "版权信息",
    "bg_color" : "#FFFFFF",
    "show_qrcode" : true,
    "theme" : "default"
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| start\_time | 直播开始时间 | datetime | 否 |  |
| pc\_logo | PC端视频LOGO地址 | string | 否 |  |
| mobile\_logo | 移动端视频LOGO地址 | string | 否 |  |
| banner | banner地址 | string | 否 |  |
| cover\_image | 频道图标地址 | string | 否 |  |
| live\_img | 直播窗口背景地址 | string | 否 |  |
| footer | 底部版权信息 | string | 否 |  |
| bg\_color | 观看页背景色 | string | 否 | 请传RGB颜色，如：rgb\(255,255,255,1\)或十六进制颜色码 |
| show\_qrcode | 是否显示手机观看二维码 | bool | 否 | 传true为显示，false为不显示 |
| theme | 观看页主题 | string | 否 | 传default为默认主题，tech为科技版，默认为default |

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
    "footer": "技术支持：目睹直播技术开发团队",
    "bg_color": "#dfebf1",
    "show_qrcode": false,
    "theme": "default"
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
| bg\_color | 观看页背景色 | string |
| show\_qrcode | 是否显示手机观看二维码 | bool |
| theme | 观看页主题 | string |
| hls\_play\_addr | hls播放地址\(仅流量版用户有该字段\) | string |
| rtmp\_play\_addr | rtmp播放地址\(仅流量版用户有该字段\) | string |



