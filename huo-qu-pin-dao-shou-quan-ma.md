# 获取频道授权码 {#获取频道授权码}

#### 请求header {#请求header}

```
POST /v1/activities/{频道id}/getAuthKey
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 返回 {#返回}

```
{
  "status": "y",
  "msg": "获取成功",
  "authkey": "abcdefg"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| status | 获取结果 | string | y为成功，n为失败 |
| msg | 结果描述 | string |  |
| authkey | 授权码 | string |  |



