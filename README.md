# SpringCloudAlibaba
SpringCloudAlibaba

SpringCloudAlibaba项目介绍

项目使用：springboot+SpringCloud+AlibabaCloud
开发系统使用Linux Centos 8(虚拟机)
中间件使用：
Nacos,Sentinel,SpringCloud Gateway,Sleuth+Zipkin+Feign
Nacos做注册中心和配置中心，
Sentinel做限流降级
Gateway做服务网关
Feign做服务间调用
Sleuth+Zipkin做链路追踪

项目模块主要包括视频模块，订单模块，用户模块。
项目代码目录：



![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba1.png)


Nacos的使用：
引入依赖并进行配置

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba2.png)
![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba3.png)
![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba5.png)

启动类上加注解

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba6.png)

在其他服务中使用

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba7.png)

Nacos的页面

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba8.png)

使用open-Feign实现远程方法调用：
导入依赖

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba9.png)
![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba10.png)

订单服务中远程调用视频服务

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba11.png)

使用sentinel实现服务的限流，熔断和降级。
引入依赖以及进行配置：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba12.png)
![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba13.png)

Sentinel页面中进行限流操作

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba14.png)

Sentinel页面中配置熔断策略：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba15.png)

降级后使用feign和sentinel的整合，对降级后的返回用户一个提前准备的兜底数据。
开启feign对sentinel的支持：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba16.png)

创建容错类：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba17.png)

在原来Video类中添加注解：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba18.png)

创建Gateway：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba19.png)

添加依赖以及配置：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba20.png)
![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba21.png)

使用Gateway的全局过滤器实现用户鉴权:

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba22.png)

使用Sleuth+Zipkin实现链路追踪：
导入依赖以及配置：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba23.png)
![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba24.png)

Zipkin界面：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba25.png)

Zipkin的日志持久化：

![Image text](https://github.com/forestsss/img-folder/blob/765e0538c4e0ac624d260ede6956cbc2c556b131/springcloudAlibaba26.png)
