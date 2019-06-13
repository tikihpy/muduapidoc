# 获取暂存视频列表 {#获取暂存视频列表}

#### 请求header {#请求header}

```
GET /v1/videos/temp
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

#### 可选参数 {#可选参数}

`title=视频名称&act_id=暂存视频所属频道id&manager=频道管理员ID&perPage=每页显示条数&p=页码`

#### 可选参数说明 {#可选参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| title | 视频名称，支持模糊查询 | string |
| act\_id | 暂存视频所属频道id | integer |
| manager | 频道管理员ID | integer |
| perPage | 每页显示条数，默认10条 | integer |
| p | 页码，默认第一页 | integer |

注：当不传`act_id`参数时会返回当前用户所有频道的暂存视频

#### 返回 {#返回}

```
{
    "videos": [
        {
            "id": 88806,
            "act_id": 10001589,
            "duration": 221,
            "start_time": "2019-02-19 13:57:55",
            "end_time": "2019-02-19 14:01:36",
            "camera_id": 0,
            "url": "https://myun-hw-s3.myun.tv/vobrpnep/xyl4aoln/on25l9zn/4xmpdo1x_1550556122579360080_360p.m3u8",
            "m3u8": "https://myun-hw-s3.myun.tv/vobrpnep/xyl4aoln/on25l9zn/4xmpdo1x_1550556122579360080_360p.m3u8",
            "thumb": "https://myun-hw-s3.myun.tv/vobrpnep/ndy7e3dn/1550556099348209136.jpg",
            "size": 0,
            "width": null,
            "height": null,
            "mod_name": "111120190219135755",
            "moved": 0,
            "dateline": "1550555875",
            "status": 0,
            "delete_time": null,
            "act_manager_id": 0
        },
        {
            "id": 88802,
            "act_id": 10001589,
            "duration": 225,
            "start_time": "2019-02-19 13:42:58",
            "end_time": "2019-02-19 13:46:43",
            "camera_id": 0,
            "url": "https://myun-hw-s3.myun.tv/vobrpnep/x45op1zb/lx7gezmx/6ng0ko8b_1550555218788933472_360p.m3u8",
            "m3u8": "https://myun-hw-s3.myun.tv/vobrpnep/x45op1zb/lx7gezmx/6ng0ko8b_1550555218788933472_360p.m3u8",
            "thumb": "https://myun-hw-s3.myun.tv/vobrpnep/xkj1r87n/1550555204857290660.jpg",
            "size": 0,
            "width": null,
            "height": null,
            "mod_name": "111120190219134258",
            "moved": 0,
            "dateline": "1550554978",
            "status": 0,
            "delete_time": null,
            "act_manager_id": 0
        }
    ],
    "meta": {
        "total": 5,
        "page": 1,
        "current": 1,
        "auto_save_live_video": false
    },
    "links": {
        "next_url": null,
        "end_url": "http://api.mudu.tv/v1/videos/temp?&p=1&act_id=10001589&perPage=10"
    }
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| videos | 暂存视频列表\(每页10个\) | json array |
| meta | 暂存视频列表其他信息 | json array |
| links | 暂存视频列表信息 | json array |
| id | 暂存视频id | integer |
| act\_id | 暂存频道id | integer |
| duration | 暂存视频长度\(秒\) | integer |
| start\_time | 暂存视频开始时间 | datetime |
| end\_time | 暂存视频结束时间 | datetime |
| url | 暂存视频原始地址 | string |
| m3u8 | 暂存视频m3u8地址 | string |
| thumb | 暂存视频封面地址 | string |
| size | 暂存视频大小\(字节\) | integer |
| width | 暂存视频宽度 | integer |
| height | 暂存视频高度 | integer |
| mod\_name | 暂存视频名字 | string |
| moved | 是否被用户移动到视频库，默认0为没有移动，1为已经移动 | integer |
| dateline | 生成时间戳 | string |
| status | 暂存视频状态，文件状态，0为正常，1为已删除 | integer |
| delete\_time | 暂存视频删除时间 | datetime |
| act\_manager\_id | 频道管理员ID，视频所属非频道管理员时值为0 | integer |
| total | 暂存视频总个数 | integer |
| page | 暂存视频总页数 | integer |
| current | 当前暂存视频页数 | integer |
| auto\_save\_live\_video | 是否自动移到媒体库 | boolean |
| next\_url | 下一页地址 | string |
| end\_url | 最后一页地址 | string |



