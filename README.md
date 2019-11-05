# DataBaseHub
## 软件工程毕业设计小结
利用python flask实现了前端页面，使用网上down下的网页模板，将页面接收到的请求翻译为docker命令，从而控制后台docker容器的启动，由于笔记本性能有限，暂未将docker与k8s结合。
## 后台数据库 mysql+hbase
mysql数据库，一些需要计算的数据存放到mysql数据库中，mysql数据库可以跑在docker里，此外，docker image包含hbase列数数据库，同样可以利用python对接hbase操作数据。
## 前后端交互 ajax+websocket+echart
利用表单和ajax技术，进行交互。监控页面中使用了websocket将后台的实时监控数据与前端的echart框架结合，将计算机的硬件信息在首页上实时展现。
## docker调度
通过异步线程来将前端接收到的指令与docker api结合
## 决策支持
本人统计学知识不足，只是简单地使用鸢尾花分类模型，将决策支持中的几个要素固化到数据中，通过前端接收变量，传到后端，利用训练好的数据模型进行计算。
## 容器自动部署
支持通过页面中自动化部署zookeeper、kafka、flume、sqoop、hbase、notebook应用，notebook提供python2、python3在线编程环境，并且在其中放置了数据可视化教程、数据挖掘案例。
其中微服务中存在依赖关系zk-->kafka，zk-->hbase，notebook为单体应用无依赖。
## 流式数据处理spark streaming
利用spark streaming设置时间窗口，以每个时间窗口内的数据作为源数据，实现流上机器学习，不断完善数据模型。部署在本地的spark streaming实时监控websocket中传输的数据，接收之后按照批次打包放置在默认文件路径下，由Flume对此文件路径进行实时监控，并实时采集数据，将数据传输到docker容器中kafka producer，然后由kafka customer将数据写入hbase，hbase作为数据仓库，完成对于数据的存储和管理。
