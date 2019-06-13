# 获取频道报名数据 {#获取频道报名数据}

#### 请求header {#请求header}

```
 POST /v1/activities/{频道id}/signupRecord
 Authorization:Bearer {ACCESS TOKEN}
 Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

```
{
     "start_time" : "2016-12-28 19:00:00",
     "end_time" : "2016-12-29 09:55:48",
     "perPage" : 10,
     "p" : 1
 }
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| start\_time | 指定报名开始时间 | datetime | 否 | 如：2016-12-20 10:00:00 |
| end\_time | 指定报名结束时间 | datetime | 否 | 如：2016-12-22 18:00:00 |
| perPage | 每页结果数 | integer | 否 | 默认20，最大100 |
| p | 页码 | integer | 否 | 默认1 |

#### 返回 {#返回}

```
{
    "totalCount": 1,
    "data": [
        [
            "15100246756n5mzn72hk",
            "浙江省网友",
            "13000000000",
            "B(B)",
            "A(A)",
            "简答题回答A",
            "简答题回答B",
            "2017-11-07 11:18:20"
        ]
    ],
    "headers": [
        "用户ID",
        "昵称",
        "手机",
        "题目一:问题A",
        "题目二:问题B",
        "问答题A",
        "问答题B",
        "报名时间"
    ]
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| totalCount | 报名总数 | integer |
| data | 报名数据 | json array |
| headers | 报名表头 | json array |



