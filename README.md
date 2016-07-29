# kafka-graphite-0.10
kafka metrics  to graphite



Kafka Graphite Metrics Reporter

支持  Kafka 0.10.0 发送metrics 到graphite 

首先 maven 打包 项目
 “mvn package”
 
复制 “kafka-graphite-1.0.0-SNAPSHOT.jar” jar 包到 libs/ 文件夹下面


修改borker 的 server.properties  如下所示

重新启动broker

metric.reporters=org.apache.kafka.common.metrics.GraphiteReporter \n
kafka.metrics.polling.interval.secs=60 (发送metrics到graphited 频率 单位是秒) \n
kafka.graphite.metrics.reporter.enabled: true (default: false)
kafka.graphite.metrics.host: 192.168.0.1 (default: localhost)
kafka.graphite.metrics.port: 2003 (default: 2003)
kafka.graphite.metrics.prefix: kafka (default: kafka)
kafka.graphite.metrics.include: (kafka.network.*|kafka.*.topic.*) (default: null  匹配哪些metrics发送)
kafka.graphite.metrics.exclude:  (default: null 和上面相反)


