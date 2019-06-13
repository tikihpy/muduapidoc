# 获取观众观看流水 {#获取观众观看流水}

#### 2018年12月1号前的数据流水接口参考[获取观众观看流水](http://mudu.tv/api/v1/ACTIVITY_USER_RECORDS.html) {#2018年12月1号前的数据流水接口参考-获取观众观看流水}

#### 请求header {#请求header}

```
 POST /v2/activities/{频道id}/userRecords
 Authorization:Bearer {ACCESS TOKEN}
 Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

`本接口每日调用上限为10次，次日0点重置`

```
{
     "start_time" : "2016-12-28 19:00:00",
     "end_time" : "2016-12-29 09:55:48",
     "perPage" : 10,
     "p" : 1,
     "filter_watch_time" : 1
 }
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| start\_time | 指定开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| end\_time | 指定结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |
| filter\_watch\_time | 是否过滤未观看观众 1为是，0为否 | integer | 否 | 默认1 |

#### 返回 {#返回}

```
   [
       {
           "record_id": 100,
           "assign_id": "第三方id",
           "user_id": "123",
           "nick": "浙江省网友",
           "addr": "浙江杭州",
           "online_time": "00:02:00",
           "watch_time": "00:01:00",
           "phone": "13000000000",
           "first_login_time": "2018-03-15 15:33",
           "last_online_time": "2018-03-15 15:34",
           "device": "移动端",
           "browser": "QQ浏览器",
           "origin": "直接访问"
       },
       {
           "record_id": 101,
           "assign_id": "第三方id",
           "user_id": "456",
           "nick": "江苏省网友",
           "addr": "江苏南京",
           "online_time": "00:06:00",
           "watch_time": "00:05:00",
           "phone": "13000000000",
           "first_login_time": "2018-03-15 13:31",
           "last_online_time": "2018-03-15 13:36",
           "device": "电脑端",
           "browser": "谷歌浏览器",
           "origin": "直接访问"
       }
   ]
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| record\_id | 观众观看流水id | integer |
| user\_id | 观众id | string |
| assign\_id | 观众id | 第三方id |
| nick | 观众昵称 | string |
| addr | 观众地址 | string |
| online\_time | 在线时长 | datetime |
| watch\_time | 观看时长 | datetime |
| phone | 手机号 | string |
| first\_login\_time | 进入时间 | datetime |
| last\_online\_time | 离线时间 | datetime |
| device | 观看设备 | string |
| browser | 观看方式 | string |
| origin | 访问来源 | string |



