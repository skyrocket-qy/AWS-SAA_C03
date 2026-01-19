# Deployment Strategies

For the SAA-C03 exam, it is crucial to understand different deployment strategies and which AWS services support them.

## 1. Canary Deployment

**Canary Deployment** involves releasing a new version of your application to a small percentage of users (a "canary") to test for issues before rolling it out to everyone.

- **How it works**: Traffic is split (e.g., 90% to V1, 10% to V2). If the 10% don't report errors, you gradually increase traffic to V2 until it hits 100%.
- **AWS Services**:
    - **API Gateway**: Supports "Canary Release" on a specific stage. You can adjust the % of traffic sent to the canary.
    - **AWS Lambda**: Use **Aliases** and **Traffic Shifting** (via CodeDeploy) to shift traffic from one version to another (Linear or Canary).
    - **Application Load Balancer (ALB)**: Can use weighted target groups to route traffic (e.g., Target Group A = 90%, Target Group B = 10%).

## 2. Blue/Green Deployment

**Blue/Green Deployment** creates two identical environments. One (Blue) runs the current application, and the other (Green) runs the new version.

- **How it works**: You deploy V2 to Green. Once tested, you switch ALL traffic from Blue to Green instantly.
- **Benefits**: Zero downtime, easy rollback (just switch traffic back to Blue).
- **AWS Services**:
    - **Elastic Beanstalk**: Swap Environment URLs (CNAME swap).
    - **Route 53**: Weighted routing policy (can mimic Blue/Green by flipping 100% weight).
    - **CodeDeploy**: Supports Blue/Green for EC2, Lambda, and ECS.
    - **RDS**: Create a Read Replica, upgrade it, and then promote it to Primary (manual Blue/Green for databases).

## 3. Rolling Deployment

**Rolling Deployment** updates instances in batches.

- **How it works**: A batch of instances is taken out of service, updated (or replaced), and put back in.
- **Pros**: No downtime, requires fewer resources than Blue/Green.
- **Cons**: Deployment takes longer; rolling back is slower.
- **AWS Services**:
    - **Elastic Beanstalk**: Rolling, Rolling with Additional Batch.
    - **EC2 Auto Scaling**: Instance Refresh.

## 4. All-at-Once

**All-at-Once** deploys the new version to all instances simultaneously.

- **Pros**: Fastest deployment.
- **Cons**: **Downtime** is inevitable while the restart happens.
- **AWS Services**: Elastic Beanstalk.

---

## Exam Comparison Table

| Strategy | Cost | Downtime | Rollback Speed | Analysis |
| :--- | :--- | :--- | :--- | :--- |
| **All-at-Once** | Lowest | **Yes** | Slow | None |
| **Rolling** | Low | No | Slow | Limited |
| **Blue/Green** | **High** (Double resources) | No | **Instant** | Full environment test |
| **Canary** | Low/Medium | No | Fast | **Real user data** |

---

## Exam Tips

- **API Gateway**: If the question mentions "Canary," "Stage Variables," or "Traffic %," think **API Gateway**.
- **Lambda**: If the question asks to shift traffic gradually over time (e.g., 10% every 10 minutes) for a serverless function, use **CodeDeploy with Lambda Aliases**.
- **Instant Rollback**: If the requirement is "immediate rollback" in case of failure, **Blue/Green** is the best answer.
- **Minimize Cost**: If cost is the primary factor and some downtime is acceptable, **All-at-Once** is the answer. If no downtime is allowed but cost is still a concern, **Rolling**.
