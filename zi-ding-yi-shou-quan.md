# 自定义授权 {#自定义授权}

### 功能说明 {#功能说明}

目睹直播提供了一系列的授权观看方式，如密码验证，付费观看等，然而由于客户业务的多样性，实现如：接入客户自身账户体系，登陆OA系统后再跳转到目睹观看直播等一系列更高级的授权观看方式，此时就需要使用自定义授权。



_【自定义授权流程，这里应该有个自定义授权流程图】_



### 功能设置 {#功能设置}

首先，需在`某个频道 - 频道管理 - 授权观看 - 授权类型`中点击自定义授权，并输入您希望在观众进入观看页时跳转的链接，如：

`http://your-domain/auth.php`

提交后自动生成频道唯一的密钥key

### 跳转说明 {#跳转说明}

设置完成后，观众进入该频道观看页时会自动跳转到设置的链接

### 观众身份有效期 {#观众身份有效期}

有效期默认为7天

#### 请求header {#请求header}

```
GET http://{your-domain}/auth.php
```

#### 参数说明 {#参数说明}

| 参数 | 参数说明 | 参数类型 | 备注 |
| :--- | :--- | :--- | :--- |
| visitorId | 观众唯一身份标识ID | string |  |
| notify\_url | 直播观看链接 | string | 已urlencode |

### 验证回调 {#验证回调}

客户在己方页面上进行自定义的逻辑验证，如：登录OA，填写手机号，关注，买票等，验证通过后跳转到上方获取的`notify_url`,并携带加密参数key

#### 请求header {#请求header}

```
GET http://mudu.tv/watch/123456
```

注：跳转的url请使用您获取的notify\_url并urldecode

#### 参数说明 {#参数说明}

| 参数 | 参数说明 | 参数类型 | 备注 |
| :--- | :--- | :--- | :--- |
| key | 加密参数 | string |  |
| expire | 授权过期时间 | integer | 过期的秒数 如:一小时后过期则传3600 |

key的生成方法（以PHP为例）：

```
md5(visitorId.频道密钥)
```

#### PHP DEMO {#php-demo}

```
<?php
const AUTHKEY='控制台获取的密钥';

$visitorId = $_GET['visitorId'];
$notifyUrl = $_GET['notify_url'];

if(true) { //todo:增加客户自己的验证逻辑,例如登录,关注,付费,填手机号等
    $key = md5($visitorId.AUTHKEY);
    if(strpos($notifyUrl,'?') !== false){//url参数处理,将key加到url参数中
        $returnUrl = $notifyUrl."&key=".$key."&expire=3600";
    }else{
        $returnUrl = $notifyUrl."?key=".$key."&expire=3600";
    }
    header("Location:".$returnUrl);//跳转到直播观看页
}
```



