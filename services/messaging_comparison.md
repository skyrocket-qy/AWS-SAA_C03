# Comparison: SQS vs. Amazon MQ vs. Amazon MSK

| Feature | **Amazon SQS** | **Amazon MQ** | **Amazon MSK** |
| :--- | :--- | :--- | :--- |
| **Primary Use**| Cloud-native decoupling | Migrating legacy brokers | Real-time event streaming |
| **Protocols** | AWS HTTP API | AMQP, MQTT, STOMP | Kafka (TCP) |
| **Scaling** | **Infinite/Serverless** | Limited by instance | Cluster/Broker based |
| **Legacy App** | No | **Yes** (ActiveMQ/RabbitMQ) | No |
| **High Throughput**| Medium/High | Low/Medium | **Ultra-High** |
