# 身份赋予API {#身份赋予api}

### 功能说明 {#功能说明}

身份赋予API可以在客户在直播时，指定观众以特定身份观看直播，如将自身平台的观众身份传递到直播页面，让观众获得无缝的体验。

特别说明：如果您选用了此API，那么微信打赏，付费观看等涉及微信的功能将暂不可用

### 接口说明 {#接口说明}

#### 请求header {#请求header}

```
GET http://{your-domain}/activity.php?a=userAssign
```

注：请将`{your-domain}`替换为您的域名，或者`mudu.tv`

#### 参数说明 {#参数说明}

| 参数 | 参数说明 | 参数类型 | 是否必填 | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| id | 频道id | integer | 是 | 频道id是控制台进入频道 直播控制页面后，url中的id参数 |
| userid | 观众唯一身份标识ID | string | 否 | 如果传此参数，务必要保证其唯一性 |
| name | 观众昵称 | string | 是 |  |
| avatar | 观众头像url | string | 否 | 必须urlencode |
| key | 自定义加密key | string | 是 | key生成方法见下方 |
| expire | 过期时间（秒） | integer | 否 | 默认为7天，如想指定有效期为1小时，则传3600 注意，最大值为2147483647，否则无效 |

key的生成方法（以PHP为例）：

```
$userid  = 'my_company_user_12345';
$authKey = 'ABCDEFG';
$key     = md5($user_id.$authKey);
```

注：此处的`$authKey`请在`某个频道 - 频道管理 - 授权观看 - 授权类型 - 自定义授权`中获取

### PHP DEMO {#php-demo}

```
# 直播频道ID：         12345
# 观众唯一身份标识ID：  my_company_user_12345
# 观众名称：           我的公司_观众A
# 观众头像：           http://your-domain/avatar.png
# 密钥：               ABCDEFG

<?php
$params = [
    'id'     => '12345',
    'userid' => 'my_company_user_12345',
    'name'   => '我的公司_观众A',
    'avatar' => 'http://your-domain/avatar.png',
    'key'    => md5('my_company_user_12345ABCDEFG')
];
header('Location:http://mudu.tv/activity.php?a=userAssign&'.http_build_query($params));
```



