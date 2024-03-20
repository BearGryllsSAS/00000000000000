# 网络聊天室

相关概念参考：

- [维基百科-网络聊天室](https://zh.m.wikipedia.org/wiki/%E7%B6%B2%E8%B7%AF%E8%81%8A%E5%A4%A9%E5%AE%A4 "点击跳转维基百科页面")
- [百度百科-网络聊天室](https://baike.baidu.com/item/%E7%BD%91%E7%BB%9C%E8%81%8A%E5%A4%A9%E5%AE%A4/2324705?_swebfr=220011 "点击跳转百度百科页面")

## 项目简介

在这个梦幻般的网络公共聊天室中，我倾注了毕生的心血，打造了一个令人惊叹的交流空间。这个聊天室拥有着无与伦比的性能和高效的并发处理能力，让每一次互联网冒险都变得如丝般顺滑。无论您是匆匆路过的游客，还是渴望分享心情的常驻用户，这里都将成为您畅谈的乐园。登录、注册、畅聊，一切尽在指尖之间。选择成为会员，更将开启一段独特的旅程，尽享专属特权和精彩体验。在这个充满活力和可能性的聊天室里，每一次交流都是一场启发灵感的冒险，每一次登录都是一次奇妙的邂逅。这里融合了技术的力量和人性的温暖，成就了一个真正意义上的数字家园，期待您的加入，共同书写属于我们的精彩故事。

## 系统架构图

项目主体骨架基于非阻塞`Socket`+`Epoll`网络监听体系，使用线程池处理与客户端数据的收发，采用`MySQL`数据库连接池封装多个`MySQL`对象进行数据持久化管理，采用基于升序链表的定时器记录客户端的活跃状态以避免资源浪费，同时实现了同步/异步日志系统记录服务器运行状态。

![architecture](./documents/00、preview-pic/architecture.jpg)

## 项目结构说明
>  网络聊天室  
>
> > `documents` -- 环境搭建、编码规范、项目需求等文档资源
> > 
> > `server-cpp` -- `C++`服务器项目主体
> >
> > `.gitignore` -- 忽略提交配置
> >
> > `LICENSE` -- `Apache`许可证
> > 
> > `README-CN.md` -- 项目自述文件-中文版
> > 
> > `README-EN.md` -- 项目自述文件-英文版

## 软件架构

### 技术栈

| 技术              | 说明               | 版本                                                   | 备注                                                         |
| ----------------- | ------------------ | ------------------------------------------------------ | ------------------------------------------------------------ |
| `MySQL`           | Web框架            | `1.3.0`                                                | https://github.com/oatpp/oatpp                               |
| `MySQL Connector` | `MySQL`连接驱动库  | 8.0.27                                                 | https://dev.mysql.com/downloads/connector/cpp/<br>https://dev.mysql.com/doc/connector-cpp/1.1/en/connector-cpp-apps.html |
| `JWT`             | `JSON` Web Token   | [v1.4](https://github.com/arun11299/cpp-jwt/tree/v1.4) | https://opensourcelibs.com/lib/cpp-jwt                       |
| `OpenSSL`         | 开源安全套接层协议 | `1.1.1L`                                               | https://www.openssl.org/<br>https://www.xolphin.com/support/OpenSSL/OpenSSL_-_Installation_under_Windows |

## 环境要求

### 开发工具

| 工具            | 说明                  | 版本      | 备注                                                         |
| --------------- | --------------------- | --------- | ------------------------------------------------------------ |
| `Navicat`       | 数据库连接工具        | latest    | https://www.navicat.com.cn/                                  |
| `RDM`           | `Redis`可视化管理工具 | latest    | https://github.com/uglide/RedisDesktopManager<br>https://gitee.com/qishibo/AnotherRedisDesktopManager |
| `PowerDesigner` | 数据库设计工具        | 16.6      | http://powerdesigner.de/                                     |
| `Axure`         | 原型设计工具          | 9         | https://www.axure.com/                                       |
| `MindMaster`    | 思维导图设计工具      | latest    | http://www.edrawsoft.cn/mindmaster                           |
| `Visio`         | 流程图绘制工具        | latest    | https://www.microsoft.com/zh-cn/microsoft-365/visio/flowchart-software |
| `Apipost`       | `API`接口调试工具     | latest    | https://www.apipost.cn/                                      |
| `Mock.js`       | `API`接口模拟测试     | latest    | http://mockjs.com/                                           |
| `Git`           | 项目版本管控工具      | latest    | https://git-scm.com/                                         |
| `Codeup`        | 项目源码托管平台      | latest    | https://codeup.aliyun.com                                    |
| `Projex`        | 开发过程管控平台      | latest    | https://devops.aliyun.com/projex                             |
| `IDEA`          | `Java`开发`IDE`       | 2022.1.3+ | https://www.jetbrains.com/idea/download                      |
| `Apache Maven`  | Maven 构建工具        | 3.6.3     | https://maven.apache.org/                                    |
| `Docker Maven`  | Maven Docker插件      | 0.40.2    | https://dmp.fabric8.io/<br>https://github.com/fabric8io/docker-maven-plugin |
| `VS`            | `C++`开发`IDE`        | 2022      | https://learn.microsoft.com/en-us/visualstudio/releases/2022/release-notes |
| `Cmake`         | `C++`跨平台编译       | latest    | https://cmake.org/cmake/help/latest/index.html               |

### 开发环境

| 依赖环境  | 版本       | 备注                      |
| --------- | ---------- | ------------------------- |
| `Windows` | 10+        | 操作系统                  |
| `JDK`     | 1.8.0_191+ | https://www.injdk.cn/     |
| `NodeJS`  | 16.17.0    | https://nodejs.org/zh-cn/ |
| `NPM`     | 8.19.2     | https://www.npmjs.com/    |

### 服务器环境

| 依赖环境    | 版本                                                         | 备注                                                         |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `Anolis OS` | `8.6GA`                                                      | https://openanolis.cn/anolisos                               |
| `Docker`    | latest                                                       | https://www.docker.com/                                      |
| `MySQL`     | 8.0.20                                                       | https://www.mysql.com/cn/                                    |
| `Redis`     | 6.2.7                                                        | https://redis.io/                                            |
| `Nacos`     | 2.1.0                                                        | https://nacos.io/zh-cn/docs/quick-start-docker.html          |
| `Sentinel`  | 1.8.4                                                        | https://github.com/alibaba/Sentinel/releases                 |
| `Seata`     | 1.5.1                                                        | https://github.com/seata/seata                               |
| `RocketMQ`  | 4.9.3                                                        | https://rocketmq.apache.org/                                 |
| `Nginx`     | latest                                                       | https://nginx.org/en/                                        |
| `FastDFS`   | [V6.07](https://github.com/happyfish100/fastdfs/releases/tag/V6.07) | https://gitee.com/fastdfs100                                 |
| `ELK`       | 7.6.2                                                        | https://www.elastic.co/guide/en/elastic-stack/7.6/index.html |
| `MongoDB`   | 4.4.17                                                       | https://www.mongodb.com/try/download/community               |
| `Jenkins`   | latest                                                       | https://www.jenkins.io/zh/doc/book/installing/               |

## 特别鸣谢

`zero-one-healthy-check`的诞生离不开开源软件和社区的支持，感谢以下开源项目及项目维护者：

- `spring`：https://github.com/spring-projects
- `alibaba`：https://github.com/alibaba
- `mybatis`：https://github.com/mybatis/mybatis-3.git
- `mp`：https://github.com/baomidou
- `api`：https://gitee.com/xiaoym/knife4j
- `vue`：https://github.com/vuejs
- `ui`：https://github.com/ElemeFE
- `oatpp`：https://github.com/oatpp/oatpp
- `业务参考项目`：https://gitee.com/scmt1/healthyCheck-backend

同时也感谢其他没有明确写出来的开源组件提供给与维护者。

## 支持一下

如果觉得框架和项目还不错，点个⭐Star，这将是对**01星球**极大的鼓励与支持。

想了解更多关于计算机方向选择、学习建议等相关信息，可以关注[**01星球B站主页~**](https://space.bilibili.com/1653229811?spm_id_from=333.1007.0.0)