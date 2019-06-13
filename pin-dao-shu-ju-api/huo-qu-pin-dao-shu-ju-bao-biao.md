# 获取频道数据报表 {#获取频道报表}

#### 请求header {#请求header}

```
GET /v1/activities/{频道id}/report
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 返回 {#返回}

```
{
  "id": 1928,
  "name": "测试",
  "cost": 0,
  "watch_seconds": 0,
  "watch_times": 31,
  "watch_times_detail": {
    "海外": "31.00000",
    "total": "31.00000",
    "pc": "31.00000"
  },
  "online_peak": "2.00000",
  "comments_count": 2,
  "publish_seconds": 0,
  "online_detail": {
    "201603172120": 2,
    "201603172123": 2,
    "201603172126": 1,
    "201603172124": 1
  },
  "uv": 123,
  "pv": 123
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 频道id | integer |
| name | 频道名称 | string |
| cost | 频道消费金额 | float |
| watch\_seconds | 频道总观看时间\(秒\) | integer |
| watch\_times | 直播观看次数 | integer |
| watch\_times\_detail | 直播观看次数详情 | json array |
| total | 直播观看次数 | float |
| pc | 电脑端观看次数 | float |
| 海外\(或其他省市\) | 对应地区观看次数 | float |
| online\_peak | 人数观看峰值 | float |
| comments\_count | 频道评论总数 | integer |
| publish\_seconds | 直播总时长\(秒\) | integer |
| online\_detail | 在线人数详细信息 | json array |
| 201603172120 | 此时的在线人数 | integer |
| uv | 频道UV | integer |
| pv | 频道PV | integer |



