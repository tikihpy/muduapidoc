# 获取账户流量消费流水 {#获取账户流量消费流水}

#### 请求header {#请求header}

```
POST /v1/user/transferRunning
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

```
{
    "type" : 1,
    "startTime" : "2016-10-09 16:17:48",
    "endTime" : "2017-01-29 16:19:42",
    "perPage" : 100,
    "p" : 1
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| type | 交易类型 | integer | 是 | 可用参数如下： 1（增加记录） 2（减少记录） |
| startTime | 指定交易开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| endTime | 指定交易结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |

#### 返回 {#返回}

```
[
  {
    "order_id": 15,
    "amount": 30,
    "left_transfer": 30,
    "datetime": "2016-11-28 17:31:51",
    "description": "后台充流量,数量:10G,备注：测试！,操作人:admin"
  }
]
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| order\_id | 订单号 | integer |
| amount | 增加/减少流量（MB） | integer |
| left\_transfer | 剩余流量（MB） | integer |
| datetime | 交易时间 | datetime |
| description | 交易描述 | string |



