# 获取频道自定义菜单 {#获取频道自定义菜单}

#### 请求header {#请求header}

```
 GET /v1/activities/{频道id}/getMenu
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
    "menus": [{
        "id": 227711,
        "act_id": 10001589,
        "uin": 1000087,
        "menu_name": "菜单名称",
        "menu_order": 1,
        "menu_cate": 2,
        "act_detail": "<p>图文<\/p>",
        "pop_videos": null
    }, {
        "id": 227712,
        "act_id": 10001589,
        "uin": 1000087,
        "menu_name": "菜单名称",
        "menu_order": 2,
        "menu_cate": 3,
        "act_detail": "",
        "pop_videos": "[{\"vid\":588290,\"resolution\":\"m3u8\"},{\"vid\":588245,\"resolution\":\"m3u8\"}]"
    }]
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| id | 菜单ID | integer |
| act\_id | 频道ID | integer |
| uin | 用户ID | integer |
| menu\_name | 菜单名称 | string |
| menu\_order | 菜单排序 | integer |
| menu\_cate | 菜单类别 | integer |
| act\_detail | 图文 | string |
| pop\_videos | 视频 | string |



