# Deployment Strategies

### 1. Canary
- **Goal**: Roll out to a small % of users first.
- **Services**: API Gateway (Canary Release), Lambda (Aliases + Traffic Shifting), ALB (Weighted Target Groups).

### 2. Blue/Green
- **Goal**: Zero downtime; instant rollback by switching all traffic to a new, identical environment.
- **Services**: Route 53 (Weighted), Elastic Beanstalk (CNAME swap), CodeDeploy.

### 3. Rolling
- **Goal**: Update instances in batches (reduced capacity during deployment).
- **Services**: Auto Scaling (Instance Refresh), Elastic Beanstalk.

### 4. All-at-Once
- **Goal**: Fastest, but involves **downtime**. Best for dev/test environments.

### Exam Comparison
- **Instant Rollback?** Blue/Green.
- **Real User Testing?** Canary.
- **Minimize Cost?** All-at-Once (if downtime is okay) or Rolling.
