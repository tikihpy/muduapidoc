# 获取临时token API {#获取临时token-api}

### 功能介绍 {#功能介绍}

此API为硬件厂商提供通过目睹账号密码直接获取临时token的特殊API，请勿滥用

### 其他说明 {#其他说明}

* token有效期默认为1天，第二次获取延长7天，第三次获取延长30天，之后无法延长有效期，到期后会自动更换token。
* 注意：调用此API会覆盖控制台生成的token，请慎重使用。

### 请求域名 {#请求域名}

`mudu.tv`

#### 请求header {#请求header}

```
POST /session.php?a=ajaxGetToken
```

#### 请求payload {#请求payload}

`email=账号&password=密码`

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| emai | 账号或者Email | string | 是 |
| password | 密码 | string | 是 |

#### 返回 {#返回}

成功示例：

```
{
    "status":"y",
    "flag":100,
    "msg":"账号密码正确",
    "token":"o26r8atp8jng8ahxgpda129dfg1qskdk",
    "expire_time":"2017-10-01 09:00:00"
}
```

失败示例：

```
{
    "status":"n",
    "flag":101,
    "msg":"参数错误"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| status | 返回状态，y为成功，n为失败 | string |
| flag | 状态码（具体请看下方表格） | integer |
| msg | 状态描述 | string |
| token | 32位字符的token | string |
| expire\_time | token失效时间 | datetime |

状态码说明

| 状态码 | 说明 |
| :--- | :--- |
| 100 | 获取成功 |
| 101 | 参数错误 |
| 102 | 不存在该用户 |
| 103 | 密码错误 |



