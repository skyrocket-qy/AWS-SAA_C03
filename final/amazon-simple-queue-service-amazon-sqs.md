# Amazon Simple Queue Service (Amazon SQS)

### Function
Fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications.

### Use Case
- Decoupling producers and consumers in a web application.
- Handling spike loads by buffering requests.
- Asynchronous task processing.

### Tips
- Standard Queues (at-least-once delivery, best-effort ordering).
- FIFO Queues (exact once, first-in-first-out).
- Visibility Timeout (item hidden while being processed).
- Dead Letter Queues (DLQ) for failed messages.
