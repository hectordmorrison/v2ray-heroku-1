已经失效



# 一键部署 v2ray 到 heroku

点击下面按钮部署：
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)
- - -
- - -

## 0. 注意

部署需要注册heroku帐号，注册heroku帐号时需要梯子（否则验证码刷不出来），需要一个能正常接收验证码的邮箱（@qq.com，@163.com都不行），有条件gmail
最好，没条件这里推荐outlook <https://login.live.com/>。

shadowsocks+v2ray-plugin方案点击这里： <https://github.com/ygcaicn/ss-heroku>

## 1. 验证

服务端部署后，点 open app,能正常显示网页，地址补上V2_Path后(例如：<https://test.herokuapp.com/static>)访问显示 Bad Request，表示部署成功。

## 2. 客户端配置

二维码地址： https://test.herokuapp.com/qr_img/v2.png
(test改成自己的app名称，如果更改了V2_QR_Path，同时也要将对应的qr_img改成修改后的)

使用客户端扫描二维码即可。

**或者**

订阅地址：https://test.herokuapp.com/qr_img

在客户端中添加订阅即可

**或者**

手动配置（推荐使用二维码或者订阅的方式配置）

```sh
address: test.herokuapp.com (test替换为你的AppName)
port: 443
id: 部署时填写的UUID
AlterID： 部署是填写的AlterID，默认64
security: auto
network: ws(websocket)
传输安全：tls打开
```

客户端下载： https://www.v2ray.com/awesome/tools.html

## 3.更新 v2ray 版本

访问 https://dashboard.heroku.com/apps 选择部署好v2ray的app，如果VER变量为 latest。直接选择More --> Restart all dynos, 程序自动重启，可通过view Logs确认进度。（更新指定版本： Settings --> Reveal Config Varsapp -->VER，修改成需要的版本号，例如 3.21）

# 参考 
https://github.com/v2ray/v2ray-core

https://github.com/wangyi2005/v2ray-heroku

https://github.com/1715173329/v2ray-heroku-undone
