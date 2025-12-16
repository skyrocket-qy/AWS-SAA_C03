# Comparison: SQS vs. Amazon MQ vs. Amazon MSK

| Feature | **Amazon SQS** | **Amazon MQ** | **Amazon MSK** |
| :--- | :--- | :--- | :--- |
| **Type** | Queue (Decoupling) | Message Broker | Event Streaming |
| **Best For** | Cloud-native apps, serverless | Migrating legacy apps (ActiveMQ/RabbitMQ) | Real-time analytics, high throughput |
| consumption | pull | push(topic) | pull |
| **Protocols** | AWS API (HTTP) | AMQP, MQTT, STOMP, OpenWire | Kafka TCP |
| **Scaling** | Infinite, auto-scaling | Limited by instance type | Scaled by adding brokers/partitions |
