# 设置频道授权观看 {#设置频道授权观看}

#### 请求header {#请求header}

```
POST /v1/activities/{频道id}/setAuth
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求参数 {#请求参数}

```
{
    "method":"AUTH_CODE",
    "tip":"欢迎观看本直播",
    "code":"1234"
}
```

#### 请求参数说明 {#请求参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| method | 授权方式（默认NONE），NONE\(无限制\)、 AUTH\_CODE（验证码授权）、CUSTOM\_VERIFY（自定义授权） | string | 否 |
| tip | 验证码授权提示文字，长度限制8个中文字符或者16个英文字符，AUTH\_CODE授权方式有效 | string | 否 |
| code | 验证码授权自定义验证码，长度限制8个中文字符或者16个英文字符，AUTH\_CODE授权方式有效 | string | 否 |
| redirect\_url | 自定义授权跳转地址，CUSTOM\_VERIFY授权方式有效 | string | 否 |

注：授权方式目前支持三种：NONE\(无限制\)、 AUTH\_CODE（验证码授权）、CUSTOM\_VERIFY（自定义授权），其他授权方式暂不支持

#### 返回 {#返回}

```
{
  "status": "y",
  "msg": "设置成功"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| status | 设置结果 | string | y为成功，n为失败 |
| msg | 结果描述 | string |  |



