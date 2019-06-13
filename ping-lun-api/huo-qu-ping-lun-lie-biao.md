# 获取评论列表 {#获取评论列表}

#### 请求header {#请求header}

```
GET /v1/activity/{频道id}/comments/{页码}
Authorization:Bearer {ACCESS TOKEN}
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

\`请将"{页码}"替换为要获取的页码数值，值为0将返回第一页数据，每页20条，接口将返回当前页的page\_index,递减传递即可  
数据为正序排序，即如果有100页，则第100页是最新的数据，第一页是最老旧的数据

#### 返回 {#返回}

```
{
    "data": [
        {
            "is_admin": true,
            "is_pushed": true,
            "msg_type": 10,
            "priority": 1558604039,
            "id": 12548935,
            "user_id": "",
            "dateline": 2006-01-02T15:04:05+08:00,
            "username": "管理员",
            "message": "官方置顶评论",
            "avatar": "//static.mudu.tv/index/avatar.png",
            "title": "官方"
        },
        {
            "is_admin": false,
            "is_pushed": true,
            "msg_type": 10,
            "priority": 10,
            "id": 521483,
            "user_id": "mkzjnshg",
            "dateline": 2006-01-02T15:04:05+08:00,
            "username": "路人甲",
            "message": "真棒",
            "avatar": "//static.mudu.tv/index/avatar.png",
            "title": ""
        }
    ],
    "total": 1024,
    "page_index":42,
    "errcode": 1000,
    "msg": "OK"
}

```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 | 备注 |
| :--- | :--- | :--- | :--- |
| total | 评论总量 | integer |  |
| id | 评论id | integer |  |
| user\_id | 观众ID | string | 发送者id，管理员为空 |
| username | 昵称 | string |  |
| message | 评论正文 | string |  |
| avatar | 头像 | string |  |
| dateline | 消息发送时间 | string | RFC3339格式 |
| is\_pushed | 是否已推送到弹幕 | bool |  |
| is\_admin | 是否为管理员发出的评论 | bool |  |
| priority | 优先级 | integer | 0不显示（未审核），10：普通，置顶评论为操作的秒时间戳 |
| title | 管理员评论头衔 | string |  |
| msg\_type | 消息类型 | integer | 详见下表 |
| total | 总量 | integer |  |
|  | page\_index | 当前页码 | integer |

#### 消息类型对照表 {#消息类型对照表}

| 类型 | 标志位 | 存储类型 | 示例 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| 普通评论 | 10 | 字符串 | 真香 | 表情替换 |
| 发送普通红包 | 20 | json | {"id":"nm4dk9jm", "type":1, "name":"恭喜发财！大吉大利！", } | type 2：钉钉 |
| 发送口令红包 | 21 | json | {"id":"nm4dk9jm", "type":1, "name":"恭喜发财！大吉大利！"} | type 2：钉钉 |
| 发送竞答红包 | 22 | json | {"id":"nm4dk9jm", "name":"参与竞答领取红包！"} |  |
| 抢口令红包评论 | 31 | 字符串 | 大吉大利，今晚吃鸡 |  |
| 免费道具打赏 | 40 | json | {"src":"free.jpg". "name":"免费道具", "number":1 } |  |
| 付费道具打赏 | 41 | json | {"src":"pay.jpg". "name":"付费道具", "number":88 } |  |
| 现金打赏 | 42 | json | {"name":"赏赐", "amount":88.99 } |  |
| 图片评论 | 50 | 字符串 | abc.jpg |  |



