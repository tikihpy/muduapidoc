# 获取频道授权观看 {#获取频道授权观看}

#### 请求header {#请求header}

```
GET /v1/activities/{频道id}/getAuth
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
  "act_auth": {
        "id": 276,
        "act_id": 10001589,
        "method": "AUTH_CODE"
    }
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| status | 获取结果 | string | y为成功，n为失败 |
| msg | 结果描述 | string |  |
| act\_auth | 频道授权方式 | object |  |
| id | 授权方式id | integer |  |
| act\_id | 频道id | integer |  |
| method | 授权方式 | string |  |

注：授权方式有：NONE\(无限制\)、 AUTH\_CODE（验证码授权）、PHONE\_VERIFY（手机登记观看）、PAY\_VERIFY（付费观看）、USER\_VERIFY（观众白名单观看）、CUSTOM\_VERIFY（自定义授权）

