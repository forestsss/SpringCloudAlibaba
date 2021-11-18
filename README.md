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
![Image text]https://github.com/forestsss/img-folder/springcloudAlibaba1.png


Nacos的使用：
引入依赖并进行配置



启动类上加注解

在其他服务中使用

Nacos的页面

使用open-Feign实现远程方法调用：
导入依赖


订单服务中远程调用视频服务

使用sentinel实现服务的限流，熔断和降级。
引入依赖以及进行配置：


Sentinel页面中进行限流操作

Sentinel页面中配置熔断策略：

降级后使用feign和sentinel的整合，对降级后的返回用户一个提前准备的兜底数据。
开启feign对sentinel的支持：

创建容错类：

在原来Video类中添加注解：

创建Gateway：

添加依赖以及配置：



使用Gateway的全局过滤器实现用户鉴权:

使用Sleuth+Zipkin实现链路追踪：
导入依赖以及配置：


Zipkin界面：

Zipkin的日志持久化：


