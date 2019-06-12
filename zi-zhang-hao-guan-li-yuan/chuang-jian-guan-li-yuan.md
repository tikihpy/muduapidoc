# 创建管理员 {#创建管理员}

### 仅企业版可用 {#仅企业版可用}

#### 请求header {#请求header}

```
PUT /v1/account/createActManager
Authorization:Bearer {ACCESS TOKEN}

```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 请求payload {#请求payload}

```
{
    "username" : "管理员A",
    "cost_type" : "1",
    "cost_limit" : "1000"
}

```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 注释 |
| :--- | :--- | :--- | :--- | :--- |
| username | 管理员用户名 | string | 是 |  |
| cost\_type | 消费上限类型 | integer | 是 | 1表示时长限制，2表示流量限制 |
| cost\_limit | 消费上限量 | integer | 是 | 当cost\_type为1时单位为分钟， cost\_type为2时，单位为GB |

#### 返回 {#返回}

```
{
    "result": "success",
    "manager_id": 233,
    "msg": "创建成功"
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| result | 创建标识 | string | success为成功，fail为失败 |
| manager\_id | 管理员ID | integer | 创建成功后管理员的ID |
| msg | 描述 | string | 创建结果描述 |



