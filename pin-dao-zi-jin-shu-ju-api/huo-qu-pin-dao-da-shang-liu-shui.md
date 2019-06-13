# 获取频道打赏流水 {#获取频道打赏流水}

#### 请求header {#请求header}

```
 POST /v1/activities/{频道id}/giftRunning
 Authorization:Bearer {ACCESS TOKEN}
 Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

```
{
     "type" : "cash",
     "startTime" : "2016-12-28 19:00:00",
     "endTime" : "2016-12-29 09:55:48",
     "perPage" : 10,
     "p" : 1
 }
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| type | 打赏类型 | string | 是 | 可用参数如下： cash（现金打赏） prop（道具打赏） |
| startTime | 指定打赏开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| endTime | 指定打赏结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |

#### 返回 {#返回}

```
 [
   {
     "gift_id": 27,
     "phone": "13000000000",
     "money": "0.10",
     "uptime": "2016-12-29 09:55:46"
   }
 ]
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| visitor\_id | 观众ID | string |
| name | 观众名 | string |
| gift\_id | 道具ID | integer |
| phone | 手机号 | string |
| money | 打赏金额 | string |
| uptime | 打赏时间 | datetime |



