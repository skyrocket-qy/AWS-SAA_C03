# Auto Scaling Policy Comparison

| Policy Type | Goal | Best Use Case |
| :--- | :--- | :--- |
| **Target Tracking** | Maintain a specific metric | "Keep average CPU at 50%". Default recommendation. |
| **Step Scaling** | Incremental response | Aggressive scaling (e.g., add 2 if CPU > 60%, add 4 if > 80%). |
| **Scheduled Scaling**| Predictable timing | Weekend surges or morning/evening batch jobs. |
| **Predictive Scaling**| Proactive ML-based | Regular traffic patterns (spikes predicted 48h ahead). |
| **Simple Scaling** | Single adjustment | Legacy; use Step Scaling instead. |

### Key Exam Points
- **Target Tracking**: Simplest for maintaining metrics; automatically creates CloudWatch alarms.
- **Step Scaling**: Best for handling variable traffic with specific responses.
- **Predictive**: Uses ML to provision capacity *before* it is needed.
