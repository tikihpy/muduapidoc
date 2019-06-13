# 获取频道观众列表 {#获取频道观众列表}

#### 2018年12月1号前的数据流水接口参考[获取频道观众列表](http://mudu.tv/api/v1/ACTIVITY_VISITOR.html) {#2018年12月1号前的数据流水接口参考-获取频道观众列表}

#### 请求header {#请求header}

```
POST /v2/activities/{频道id}/visitors
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

```
 {
     "filter" : 1,
      "perPage" : 10,
      "p" : 1,
      "direction" : "desc"
  }
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| filter | 过滤未观看观众 | string | 否 | 可用参数如下： 1（过滤观看时长小于1分钟的观众） 0（显示全部观众） |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |
| direction | 排序 | string | 否 | desc：倒序；asc：正序；默认desc |

#### 返回 {#返回}

```
[
  {
    "id": 9299,
    "uin": 1,
    "name": "测试频道",
    "addr": "浙江杭州",
    "user_id": "123",
    "assign_id": "第三方id",
    "nick": "上海市网友",
    "watch_time": "00:00:00",
    "phone": "13000000000",
    "refer": "mudu.tv",
    "visit_times": 10,
    "first_login_time": "2017-04-26 13:07:25",
    "last_online_time": "2017-04-26 13:25:00",
    "device": "电脑端",
    "browser": "IE9",
    "last_ip": "127.0.0.1",
    "share_times": 5,
    "comment_count": 22
  }
]
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 频道ID | integer |
| uin | 管理员id | integer |
| name | 频道名 | string |
| addr | 地址 | string |
| user\_id | 观众ID | string |
| assign\_id | 第三方ID | string |
| nick | 观众昵称 | string |
| watch\_time | 观看时长 | string |
| phone | 手机号 | string |
| refer | 访问来源 | string |
| visit\_times | 访问次数 | integer |
| first\_login\_time | 首次进入时间 | datetime |
| last\_online\_time | 最后在线时间 | datetime |
| device | 最后观看设备 | string |
| browser | 最后观看方式 | string |
| last\_ip | 最后登录IP | string |
| share\_times | 分享次数 | integer |
| comment\_count | 聊天数 | integer |



