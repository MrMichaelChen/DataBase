# DataBaseHub
## 软件工程毕业设计小结
利用python flask实现了前端页面，使用网上down下的网页模板，将页面接收到的请求翻译为docker命令，从而控制后台docker容器的启动，由于笔记本性能有限，暂未将docker与k8s结合。
## 后台数据库
mysql数据库，一些需要计算的数据存放到mysql数据库中，mysql数据库可以跑在docker里，此外，docker image包含hbase列数数据库，同样可以利用python对接hbase操作数据。
## 前后端交互
利用表单和ajax技术，进行交互。监控页面中使用了websocket将后台的实时监控数据与前端的echart框架结合，将计算机的硬件信息在首页上实时展现。
## docker调度
通过异步线程来将前端接收到的指令与docker api结合
## 决策支持
本人统计学知识不足，只是简单地使用鸢尾花分类模型，将决策支持中的几个要素固化到数据中，通过前端接收变量，传到后端，利用训练好的数据模型进行计算。
## docker伪分布式集群自动化部署
支持通过页面中自动化部署zookeeper、kafka、hbase、notebook应用，notebook提供python2、python3在线编程环境，并且在其中放置了数据可视化教程、数据挖掘案例。
其中微服务中存在依赖关系zk-->kafka，zk-->hbase，notebook为单体应用无依赖。
