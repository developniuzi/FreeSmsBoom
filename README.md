# FreeSmsBoom
简介：免费开源的可商用短信轰炸程序,带app端,h5端和后台网页管理端

##项目正在筹备期,后端已开发完成,正在开发用户端,预计2023年3月底发布内测,代码将在TG群组公布内测,欢迎加入[FreeSmsBoom开源交流群](https://t.me/+NLpnV38lKy4wNTBl)


## 产品三大特征

1. 云任务模式,采用Swoole协程http客户端请求,以C开发的轻量级请求库代替php和用户网页端,提高性能和接口安全
2. 用户和管理的前后端完全分离,用户端采用Uniapp开发，支持IOS 安卓 H5，管理端采用Element Vue开发，后端采用hyperf+swoole
3. 加入HTTP代理,有对接示例,优化逻辑，单个手机号码一轮只使用一个，减少成本，加入自动甄别失效逻辑，防止接口发送失败


> 开源说明:
> 1. 本系统不涉及任何业务,仅用于测试和学习接口并发和轮训.
> 2. 系统开源研究，使用者请遵守自己所在国家地区的相关法律,**违反法律者与开发者无关**.
> 3. 请大家理智甄别,独立思考,好的代码总在点滴中不断成长.

## 免责声明

1. 若使用者滥用本项目,本人 **无需承担** 任何法律责任.  
2. 本程序仅供娱乐,源码全部开源,**禁止滥用** 和二次 **贩卖盈利**.  **禁止用于商业用途**.

## 技术点

1. 通过后台自行创建接口信息.  
2. 方便的测试接口和修改，统筹管理 
3. 多线程+异步任务，使用Swoole协程和HTTP客户端，性能比肩Python.  
4. 用户通过客户端订阅创建任务，后台自定义设置用户使用资格和创建任务数量.  
5. 采用Redis缓存任务,更好的突破Mysql瓶颈,达到轻松千量级任务同时在线.  
6. 完善的中间件,拒绝抓包和盗用接口.  
7. HTTP代理模式，通过演示代码自行对接，全自动化拉取和使用.
8. 首发财务系统,市面唯一一家.
9. 可指定轰炸次数, 轰炸间隔时间,轰炸最长时间.

## 安装教程

### 小白和技术一看就懂

✨本项目已经中的前后端`vendor`和 `node_modules`均已自带，下载下来就即可运行
> 说明(小白无视):
> 因为Hyperf跨版本会导致拓展冲突，所以请勿重复执行install操作

🔨作者的开发和测试环境为: 后端`Linux Centos7.6 LNMP` 前端`Win10 Pixel4xl Iphone 14PM`
> LNMP解释:
> Linux centos 7.6
> Nginx 1.22
> Mysql 5.7
> PHP 8.0(安装redis拓展 php拓展 关闭短签名 删掉所有禁用函数)
> Swoole 4.x
> Redis 6.0+

1. 下载项目并解压  
   三个目录，Server为后端代码,Admin为管理端代码,User为用户端
  > 若遇到国内网络环境下载不下来,请参见 [https://github.do/](https://github.do/) 等加速镜像.
  
2. 后端运行  

   1. 在确保LNMP环境安装完成后,在linux的数据目录如`www` or `home`里放入`Server`文件夹
   ![](https://cdn.jsdelivr.net/gh/AdminWhaleFall/SMSBoom@master/img/e.g.1.png)
   
   2. 执行以下命令
   ```shell
   cd Server
   php bin/hyperf.php start
   ```
   3. 确保服务器安全组已放行9501端口,然后访问 ip:9501 如提示 `Hello FreeSmsBoom`即代表环境正常且搭建成功 
   
   4.IP:9501就是你的接口，可自行通过域名反向代理 127.0.0.1:9501
   
3. 管理端运行  

   1. 管理端采用Vue手脚架搭建,请在本地自行安装node和git
   
   2. 执行以下命令
   ```shell
    # 进入项目目录
    cd Admin

    # 安装依赖
    npm install
    
    # 建议不要用 cnpm 安装 会有各种诡异的bug 可以通过如下操作解决 npm 下载速度慢的问题
    npm install --registry=https://registry.npm.taobao.org

    # 修改Api接口
     /src/api/config.js文件中,修改`base_url`
    
    # 本地测试开发 启动项目
    npm run dev
    
    # 本地测试完成后，打包项目
    npm run build:prod
    
   ```
   3.打包完成后，在dist文件夹就是你的管理端,上传任意服务器并访问 域名/index.html即可,无需和后端在同一服务器
4. 用户端运行  

   1. 管理端采用uniapp创建,请参考https://uniapp.dcloud.net.cn/quickstart-hx.html
   
   2. 修改API接口  
    `/common/config.js`中修改`base_url`
   ```
   3.运行,请参考uniapp https://uniapp.dcloud.net.cn/tutorial/run/run-app.html#%E8%BF%90%E8%A1%8C%E5%85%A5%E5%8F%A3


## 赞助

> 暂未筹备赞助接口 **比心ing**

## 合作

> 项目筹备期,欢迎有短信资源接口的大佬合作

## Telegram Channel (TG群组)
[FreeSmsBoom开源交流群](https://t.me/+NLpnV38lKy4wNTBl)
