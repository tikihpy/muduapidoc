# 获取账户资金流水 {#获取账户资金流水}

#### 请求header {#请求header}

```
POST /v1/user/running
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

```
{
    "type" : 1,
    "startTime" : "2016-10-09 16:17:48",
    "endTime" : "2016-10-09 16:19:42",
    "perPage" : 100,
    "p" : 1
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| type | 资金类型 | integer | 否 | 可用参数如下： 1（导播台资金流水） 2（监控矩阵资金流水） 3（延迟播出资金流水） |
| startTime | 指定交易开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| endTime | 指定交易结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |

#### 返回 {#返回}

```
[
  {
    "fee_type": 1,
    "money": "1.00",
    "uptime": "2017-01-10 13:40:01"
  }
]
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| fee\_type | 资金类型 | integer |
| money | 金额 | float |
| uptime | 交易时间 | datetime |



