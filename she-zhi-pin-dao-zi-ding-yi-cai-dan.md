# 设置频道自定义菜单 {#设置频道自定义菜单}

#### 请求header {#请求header}

```
 POST /v1/activities/{频道id}/saveMenu
 Authorization:Bearer {ACCESS TOKEN}
 Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 请求payload {#请求payload}

```
{
    "menu_name" : "视频菜单",
    "menu_cate" : 3,
    "pop_videos" : [{"vid":522323,"resolution":"m3u8_480"},{"vid":521394,"resolution":"m3u8_480"}]
}
```

#### payload参数说明 {#payload参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| menu\_id | 菜单id, 没有会创建菜单 | integer | 否 |
| menu\_name | 菜单名称, 默认值"菜单名称"，长度限制4个中文字符或者8个英文字符 | string | 否 |
| menu\_cate | 菜单类别, 1聊天互动，2图文，3视频\(默认\), 4话题互动 | integer | 否 |
| act\_detail | 图文, menu\_cate为2时有效 | string | 否 |
| pop\_videos | 视频, menu\_cate为3时有效 | array | 否 |

注1：创建频道会默认创建`聊天互动`菜单，在该菜单没有删除的情况下，调用接口创建`聊天互动`菜单会失败，另`图文菜单`存在排版等问题，建议在控制台添加。当参数`menu_id`不传时，会添加一个菜单，当所有参数都不传时，即创建一个名称为`菜单名称`的`视频菜单`，视频参数请调用[媒体库API](http://mudu.tv/api/v1/MEDIA.html)获取。

注2：`图文参数`建议通过控制台的富文本编辑器添加带有格式的文本以美化排版，纯文本在排版方面不够美观。

#### pop\_videos参数说明 {#popvideos参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 |
| :--- | :--- | :--- | :--- |
| vid | 视频id，必须是从属当前用户的合法id | integer | 是 |
| resolution | 视频分辨率 | string | 是 |

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
| menu\_id | 菜单id | integer |
| result | 保存标识 | string |



