# 删除管理员 {#删除管理员}

### 仅企业版可用 {#仅企业版可用}

#### 请求header {#请求header}

```
DELETE /v1/account/deleteActManager
Authorization:Bearer {ACCESS TOKEN}
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 请求payload {#请求payload}

```
{
    "manager_id" : 233,
    "is_delete_act" : 1
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 注释 |
| :--- | :--- | :--- | :--- | :--- |
| manager\_id | 要删除的管理员ID | integer | 是 |  |
| is\_delete\_act | 是否删除该管理员创建的频道 | integer | 是 | 1表示删除，0表示不删除 |

#### 返回 {#返回}

```
{
    "result": "success",
    "msg": "删除成功"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| result | 删除标识 | string | success为成功，fail为失败 |
| msg | 描述 | string | 删除结果描述 |



