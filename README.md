# imsdk-web-sdk
IMSDK Web SDK，由爱萌科技官方维护



## 概述
IMSDK Web SDK V1 版本，使用传统的 ajax long polling 的方式，兼容更多版本浏览器。

通过 Web SDK 可以方便实现注册、登录、收发消息

## 新手上路
### 一、获取 SDK
  
  官方下载：http://www.imsdk.im/
  
  github：https://github.com/imsdk/imsdk-web-sdk

  下载到的包里包含 Demo 和 Lib 两个目录，其中 Demo 目录为一个简单的演示页面。

  该 Lib 依赖于jquery，开发时使用版本为 jquery-2.1.4.min.js，可从下载到的文件中得到。

  移动端涉及到的表情包 IMSysface 可于 Lib 目录中找到，目前 Web 端未做处理

### 二、初始化
```
var imCli = new IMSDK( '00b6413a92d4c1c84ad99e0a', {
    onInitialized : function( appEnv ){
        console.info( '初始化环境完成，当前应用：' + appEnv.appKe
    },
    onTextReceived : function( TextMsg ){
        console.info('收到文本消息 - TextMsg');
         
    },
    onImageReceived : function( ImageMsg ){},
    onVoiceReceived : function( VoiceMsg ){},
    onSystemMsgReceived : function( SystemMsg ){}  
} );
```
### 三、发送消息
```
var userMsg = {
    'target_type' : type,
    'target' : target,
    'msg_type' : 'txt',
    'content' : msg
};
imCli.sendText( userMsg, function(data, params){
    console.log( 'send data success');
}, function(code, error, params){
});
```


## 更多信息
[IMSDK官方文档](http://docs.imsdk.im/display/dev/Web+SDK)
