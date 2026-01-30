# Comparison: Amazon API Gateway vs. AWS AppSync

### Overview
| Feature | **Amazon API Gateway** | **AWS AppSync** |
| :--- | :--- | :--- |
| **API Type** | REST, HTTP, WebSocket | GraphQL, Pub/Sub |
| **Data Fetching** | Client makes multiple calls to different endpoints | Client makes a single call with a specific schema |
| **Real-time** | WebSocket APIs | GraphQL Subscriptions (WebSockets) |
| **Security** | IAM, Cognito, Lambda Authorizers, API Keys | IAM, Cognito, OIDC, API Keys |
| **Offline Support** | No native support | Native support via AWS Amplify |
| **Complexity** | Simple for standard REST endpoints | Advanced; requires learning GraphQL schema |

### Why use AppSync Pipeline Resolvers?
In API Gateway, complex logic often requires a Lambda function to orchestrate multiple backend calls. In **AppSync**, **Pipeline Resolvers** can handle this orchestration natively by sequencing multiple "Functions" (data source operations) without needing to write a monolithic "orchestrator" Lambda.
