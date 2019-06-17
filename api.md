-------

# ROBOT

-------

## LOGIN 登录接口

-------
- URL http://robot.com/login
- TYPE POST
- REQUESTS 
```
{
  "account": "用户邮箱",
  "password": "用户密码"
}
```
- RESPONSE
```
{
  "code": 0,
  "data": {
    "msg": "code为0成功，其他为失败"
  }
}
```

-------

## UPLOAD 上传日志文件接口

-------
- URL http://robot.com/upload
- TYPE POST
- HEADERS UPLOAD-KEY:87b7cb79481f317bde90c116cf36084b
- REQUESTS 
```
图片流
```
- RESPONSE
```
{
  "code": 0,
  "url": "文件url"
}
```

-------

## UPLOADURL 上传日志信息接口

-------
- URL http://robot.com/uploadUrl
- TYPE POST
- REQUESTS 
```
{
  "taskId": "任务id",
  "reportId": "报告id",
  "logUrl": "日志url"
}
```
- RESPONSE
```
{
  "code": 0,
  "data": {
    "msg": "code为0成功，其他为失败"
  }
}
```

-------

## PERFORMANCE 上报性能数据接口

-------
- URL http://robot.com/performance
- TYPE POST
- REQUESTS 
```
{
  "taskId": "任务id",
  "reportId": "报告id",
  "stepIndex": "步骤索引",
  "cpu": "cpu占用",
  "memory": "内存占用",
  "memPer": "内存占用%",
  "uploadData": "上行流量",
  "downloadData": "下行流量",
  "errorType": "错误类型"
}
```
- RESPONSE
```
{
  "code": 0,
  "data": {
    "msg": "code为0成功，其他为失败"
  }
}
```

-------

## ERGODICITY 执行接口

-------
- URL http://robot.com/ergodicity
- TYPE POST
- REQUESTS 
```
{
  "op": 0
  "taskId": "任务id",
  "screen": "base64图片流",
  "xPos1": 1,
  "yPos1": 2,
  "xPos2": 3,
  "yPos2": 4,
  "email": "第一次调用传登录用户邮箱",
  "deviceInfo": {
    "deviceBrand": "品牌",
    "deviceModel": "名称",
    "deviceVersion": "版本",
    "displayW": "宽",
    "displayH": "高"
  },
  "appInfo": {
    "appName": "名称",
    "appPackage": "包名",
    "appVersion": "版本"
  }
}
```
```
{
  "op" 1
  "taskId": "任务id",
  "reportId": "报告id",
  "screenId": "截图id",
  "stepIndex": "步骤索引"
  "screen": "base64图片流",
  "start": "是否需要找起始页"
}
```
- RESPONSE
```
{
  "code": 0,
  "data": {
    "action": "点击还是滑动",
    "pointListA": {
      "x":1,
      "y":2,
      "index":0
    }
    "msg": "code为0成功，1为等待，2为结束，3为不操作，其他为失败"
  }
}
```