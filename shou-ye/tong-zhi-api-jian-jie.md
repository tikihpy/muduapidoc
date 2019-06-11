# 通知API简介 {#通知api简介}

#### 简介 {#简介}

为了及时将重要信息告知用户，无论是通过API还是目睹控制台，我们提供了主动推送消息的服务。

使用通知服务前需要先设置通知URL，设置方法详见[设置通知URL](http://mudu.tv/api/v1/NOTICE_SET.html)。

主动推送消息的API有：

1、[创建频道](http://mudu.tv/api/v1/ACTIVITY_CREATE.html)

2、[修改频道信息](http://mudu.tv/api/v1/ACTIVITY_UPDATE.html)

3、[修改观看页信息](http://mudu.tv/api/v1/ACTIVITY_PAGE_UPDATE.html)

4、[删除频道](http://mudu.tv/api/v1/ACTIVITY_DELETE.html)

5、[视频转码通知](http://mudu.tv/api/v1/VIDEO_TRANSCODE.html)

6、[直播文档](http://mudu.tv/api/v1/ACTIVITY_DOC.html)

在目睹控制台操作，主动推送消息的有：

1、创建频道

2、修改频道信息

3、关闭频道

4、打开频道

5、删除频道

#### 主动推送消息内容示例 {#主动推送消息内容示例}

假设设置的通知URL是`http://www.foo.com/`，那么每次调用上述API时候，会通过POST方式向该地址主动发送json Data， 发送内容如下所示。

通过API创建频道发送的内容是：

```
{
    "namespace": "activity",
    "action": "create",
    "source":"api",
    "id":22874
}

```

通过API修改频道信息发送的内容是：

```
{
    "namespace": "activity",
    "action": "update_name",
    "source":"api",
    "id":22874
}

```

通过API修改观看页信息发送的内容是：

```
{
    "namespace": "activity",
    "action": "update_page",
    "source":"api",
    "id":22874
}

```

通过API删除频道发送的内容是：

```
{
    "namespace": "activity",
    "action": "delete",
    "source":"api",
    "id":22874
}

```

通过API新增视频，转码成功后发送的内容是：

```
{
    "namespace":'video',
    "action":'transcode',
    "temp_id":98
    "id":123
}

```

通过API上传文档发送的内容是：

```
{
    "namespace": "doc",
    "action": "create",
    "source":"api",
    "id":23333,
    "status":1/0 //1：成功；0：失败
}

```

通过目睹控制台创建频道发送的内容是：

```
{
    "namespace": "activity",
    "action": "create",
    "source":"console",
    "id":22874
}

```

通过目睹控制台修改观看页信息发送的内容是：

```
{
    "namespace": "activity",
    "action": "update_page",
    "source":"console",
    "id":22874
}

```

通过目睹控制台关闭频道发送的内容是：

```
{
    "namespace": "activity",
    "action": "close",
    "source":"console",
    "id":22874
}

```

通过目睹控制台打开频道发送的内容是：

```
{
    "namespace": "activity",
    "action": "open",
    "source":"console",
    "id":22874
}

```

通过目睹控制台删除频道发送的内容是：

```
{
    "namespace": "activity",
    "action": "delete",
    "source":"console",
    "id":22874
}

```

频道推流状态改变发送的内容是：

```
{
    "namespace": "activity",
    "action": "stream",
    "status":1/0,//1：开始推流；0：推流结束
    "id":22874
}
```



