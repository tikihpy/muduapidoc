# 删除频道自定义菜单 {#删除频道自定义菜单}

#### 请求header {#请求header}

```
 DELETE /v1/activities/{频道id}/delMenu
 Authorization:Bearer {ACCESS TOKEN}
 Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

```
{
    "menu_id" : 1234
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| menu\_id | 自定义菜单id | integer | 是 |

#### 返回 {#返回}

```
{
  "menu_id": 1234,
  "result": "success"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| menu\_id | 被删除的菜单id | integer |
| result | 删除标识 | string |



