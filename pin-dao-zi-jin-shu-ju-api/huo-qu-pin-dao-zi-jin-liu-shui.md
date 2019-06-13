# 获取频道资金流水 {#获取频道资金流水}

#### 请求header {#请求header}

```
POST /v1/activities/{频道id}/costRunning
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

```
 {
      "type" : "watch",
      "startTime" : "2016-12-28 19:00:00",
      "endTime" : "2016-12-29 09:55:48",
      "perPage" : 10,
      "p" : 1
  }
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| type | 交易类型 | string | 是 | 可用参数如下： watch（观看资金消费） pull（拉流服务消费） push（第三方推流消费） sms（发送短信消费） |
| startTime | 指定交易开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| endTime | 指定交易结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |

#### 返回 {#返回}

```
[
  {
    "money": "0.040",
    "uptime": "2016-11-10 11:44:01"
  }
]
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| money | 金额 | float |
| uptime | 交易时间 | datetime |



