# AWS AppSync

A fully managed service that makes it easy to develop GraphQL APIs by handling the heavy lifting of securely connecting to data sources like DynamoDB, Lambda, and more.

### Key Exam Points
- **GraphQL**: Uses GraphQL to enable applications to fetch exactly the data they need.
- **Data Sources**: Supports DynamoDB, Amazon Aurora (Serverless), AWS Lambda, Amazon OpenSearch Service, and HTTP endpoints.
- **Real-time**: Provides real-time data updates using **WebSockets** (Subscriptions).
- **Offline Access**: Supports offline data synchronization with AWS Amplify.
- **Security**: Integrates with IAM, Amazon Cognito User Pools, API Keys, and OpenID Connect for authorization.

### Pipeline Resolvers
- **Definition**: Allows executing multiple operations (called **Functions**) in a sequential order for a single GraphQL field.
- **Structure**:
    - **Before mapping template**: Prepares the data before calling the first function.
    - **Functions**: One or more execution steps (e.g., check authorization in Lambda, then fetch data from DynamoDB).
    - **After mapping template**: Finalizes the response sent back to the client.
- **Use Case**: Ideal for complex business logic, such as data validation, authorization checks across multiple tables, or fetching data from multiple sources in a specific order.
- **Communication**: Functions share a `ctx.stash` object to pass data between them.
