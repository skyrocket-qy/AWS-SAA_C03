# Auto Scaling Policy Comparison

When configuring Amazon EC2 Auto Scaling, you can choose from several scaling policies to determine how the group scales in response to changing demand.

| Policy Type | Description | Best Use Case | Key Characteristics |
| :--- | :--- | :--- | :--- |
| **Target Tracking Scaling** | Increases or decreases the current capacity of the group based on a **target value** for a specific metric. | **Default/Recommended**. Applications that scale based on average CPU, network I/O, or request count per target. | - "Keep CPU at 50%".<br>- Easy to set up.<br>- Automatically manages CloudWatch Alarms. |
| **Step Scaling** | Increases or decreases the current capacity of the group based on a set of **scaling adjustments** (steps) that vary based on the size of the alarm breach. | Workloads with **variable load patterns** where you need different responses (e.g., add 2 instances if CPU > 60%, add 4 if CPU > 80%). | - More granular control than Simple Scaling.<br>- Does **not** enforce a cooldown period (uses warm-up time).<br>- Best for aggressive scaling. |
| **Simple Scaling** | Increases or decreases the current capacity of the group based on a **single scaling adjustment**. | **Legacy**. Use only if Step Scaling doesn't fit (rare). | - Wait for a **cooldown period** to complete before further scaling activities.<br>- Less responsive than Step Scaling. |
| **Scheduled Scaling** | Scales the application based on a **predictable schedule**. | Predictable traffic patterns (e.g., scale out every Friday morning, scale in Friday night, or before a marketing event). | - Date and time specific (Cron style). |
| **Predictive Scaling** | Uses **Machine Learning** to predict traffic and provision capacity *before* it is needed. | Regular patterns with some variability (e.g., daily spikes). | - Proactive scaling.<br>- Can range from 24 to 48 hours of forecast. |

## Exam Tips
- **Target Tracking** is usually the right answer for "maintain specific metric" (e.g., maintain average CPU at 40%).
- **Step Scaling** is preferred over Simple Scaling because it handles "flapping" better and doesn't wait for cooldowns (uses instance warm-up).
- **Scheduled Scaling** is for "known time" events (e.g., weekly batch job).
- **Predictive Scaling** is for "proactive" scaling based on historical data.
