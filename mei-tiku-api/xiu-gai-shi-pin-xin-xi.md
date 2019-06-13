# 修改视频信息 {#修改视频信息}

#### 请求header {#请求header}

```
PUT /v1/videos/{视频id}
Authorization:Bearer {ACCESS TOKEN}
Content-Type:application/json
```

注：

`请将上方的{ACCESS TOKEN}替换为您的ACCESS TOKEN`

`请将"{视频id}"替换您需要获取的视频id`

参数：

```
{
    name:"文件新名字"
}

```

成功返回：

```
{
  result: "success"
}

```

失败返回：

```
{   
    errors:{
        code:'错误码',
        message:'错误信息'
    }
}
```



