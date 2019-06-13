# 获取频道发红包/抢红包记录 {#获取频道发红包抢红包记录}

#### 请求header {#请求header}

```
POST /v1/activities/{频道id}/redpack
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

```
 {
     "type" : "send",                      //send（发红包记录）,grab（抢红包记录）
     "startTime" : "2016-12-28 19:00:00",
    "endTime" : "2016-12-29 09:55:48",
      "perPage" : 10,
      "p" : 1
  }
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| type | 记录类型 | string | 是 | 可用参数如下： send（发红包记录） grab（抢红包记录） |
| startTime | 指定红包发送/抢的开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| endTime | 指定红包发送/抢的结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |

#### 返回 {#返回}

* 发红包记录
  ```
  [
  {
    "id": 7,
    "act_name": "testtest",
    "send_time": "2016-12-28 11:04:37",
    "amount": 4,
    "count": 2,
    "grab_amount": 0,
    "grab_count": 0
  }
  ]
  ```

发红包记录返回参数说明

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 红包ID | integer |
| act\_name | 频道名 | string |
| send\_time | 红包发送时间 | datetime |
| amount | 红包金额\(分\) | integer |
| count | 红包个数 | integer |
| grab\_amount | 领取金额\(分\) | integer |
| grab\_count | 领取个数 | integer |

* 抢红包记录

  ```
  [
  {
    "id": 3,
    "name": "浙江省网友",
    "user_id": "123456789abcdef",
    "grab_time": "2016-12-21 23:33:33",
    "amount": 0.01,
    "paied": 0
  }
  ]
  ```

  抢红包记录返回参数说明

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 红包ID | integer |
| name | 抢到观众 | string |
| user\_id | 抢到观众ID | string |
| grab\_time | 抢到红包时间 | datetime |
| amount | 抢到金额\(分\) | float |
| paied | 是否入账，1为已入账，0为未入账 | integer |



