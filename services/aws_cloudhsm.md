# AWS CloudHSM

**AWS CloudHSM** is a cloud-based hardware security module (HSM) that enables you to easily generate and use your own encryption keys on the AWS Cloud.

## Key Features

- **Dedicated Hardware**: You have exclusive use of the HSM instance. It is not shared with other customers.
- **FIPS 140-2 Level 3**: Provides a higher level of security compliance than KMS (which is Level 2 for the multi-tenant HSMs).
- **Customer Controlled**: You are the only one who can access your keys. AWS has no administrative access to the keys inside your HSM.
- **VPC Integrated**: CloudHSM clusters run inside your VPC, making them easily accessible from your EC2 instances.
- **Standard APIs**: Supports industry-standard APIs like PKCS#11, Java Cryptography Extensions (JCE), and Microsoft CryptoAPI (CNG).

## High Availability

CloudHSM clusters are highly available by default when you add HSMs in different Availability Zones (AZs) within a Region.
- AWS handles the synchronization of keys between the HSMs in your cluster.
- If one HSM fails, the others continue to serve requests, and AWS will automatically replace the failed unit.

---

## CloudHSM vs. AWS KMS

| Feature | AWS KMS | AWS CloudHSM |
| :--- | :--- | :--- |
| **Tenancy** | Multi-tenant HSMs | **Dedicated HSMs** |
| **Compliance** | FIPS 140-2 Level 2 (mostly) | **FIPS 140-2 Level 3** |
| **Management** | Shared Management (AWS/User) | **User Managed** (AWS manages hardware only) |
| **Access** | IAM Policies / Key Policies | **HSM Users** (Managed inside the HSM) |
| **Cost** | Flexible, pay-per-use | Higher, **hourly charge per HSM instance** |
| **Integration** | Native integration with most AWS services | Requires manual configuration for most services |

---

## Exam Tips

- **FIPS 140-2 Level 3**: If a question mentions this specific compliance requirement, the answer is almost always **CloudHSM**.
- **Dedicated Hardware**: If the requirement is for keys to be stored on dedicated, single-tenant hardware, choose **CloudHSM**.
- **No AWS Access**: If the customer must have *exclusive* control over the keys such that AWS admins cannot access them, use **CloudHSM**.
- **Management Overhead**: Remember that CloudHSM comes with significantly more management overhead than KMS (backups, user management inside the HSM, scaling).
