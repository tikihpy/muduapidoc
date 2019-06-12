# 定制频道观看地址 {#定制频道观看地址}

| 类型 | 备注 |
| :--- | :--- |
| internal\_mobile | 国内手机 |
| internal\_pc | 国内PC |
| intranet\_mobile | 内网手机 |
| intranet\_pc | 内网PC |
| oversea\_mobile | 国外手机 |
| oversea\_pc | 国外PC |

## 获取定制列表 {#获取定制列表}

### 请求header {#请求header}

```
GET /v1/activities/{频道id}/watchUrl
Authorization:Bearer {ACCESS TOKEN}
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`  
`请将"{频道id}"替换您需要获取的频道id`

### 返回 {#返回}

```
{
    "status": "y",
    "msg": "",
    "data": {
        "internal_mobile": [
            {
                "id": 114197,
                "address": "http://xxx"
            }
        ],
        "oversea_pc": [
            {
                "id": 118752,
                "address": "rtmp://xxx"
            }
        ]
    }
}
```

### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| status | 请求结果，成功为"y"，失败为"n" | string |
| msg | 结果描述 | string |
| data | 定制地址列表 | array |

## 添加定制列表 {#添加定制列表}

### 请求header {#请求header}

```
PUT /v1/activities/{频道id}/watchUrl
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

### 请求payload {#请求payload}

```
{
    "type":"intranet_mobile",
    "address":"http://192.168.2.1/watch/1xw0mr.m3u8",
    "description":"描述文本"
}
```

### 返回 {#返回}

```
{
    "status": "y",
    "msg": "操作成功"
}
```

## 删除定制列表 {#删除定制列表}

### 请求header {#请求header}

```
DELETE /v1/activities/{频道id}/watchUrl
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

### 请求payload {#请求payload}

```
{
    "id":要删除的id
}
```

### 返回 {#返回}

```
{
    "status": "y",
    "msg": "操作成功"
}
```



