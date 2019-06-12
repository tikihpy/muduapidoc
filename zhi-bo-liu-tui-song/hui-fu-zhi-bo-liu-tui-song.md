# 恢复直播流推送 {#恢复直播流推送}

_使用此API功能后，对应被禁止直播流推送的频道将恢复推流，拉流。_

#### 请求header {#请求header}

```
POST /v1/activity/{频道id}/resume
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{频道id}"替换您需要获取的频道id`

#### 返回 {#返回}

```
{
    "status":"y"
}
```

#### 返回参数说明 {#返回参数说明}

| 参数 | 描述 | 类型 |
| :--- | :--- | :--- |
| status | 成功恢复直播流推送 | string |



