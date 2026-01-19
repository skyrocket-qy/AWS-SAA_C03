# Amazon WorkDocs

**Amazon WorkDocs** is a fully managed, secure enterprise content creation, storage, and collaboration service. It allows users to easily create, edit, and share content, and because it’s stored centrally on AWS, it can be accessed from any location.

## Key Features

- **Document Collaboration**: Users can comment on files, track version history, and request feedback from both internal and external collaborators.
- **Secure Storage**: All data is encrypted at rest (using **AWS KMS**) and in transit.
- **WorkDocs Drive**: A desktop client that lets users access their WorkDocs files as a virtual drive on Windows or macOS without using local disk space.
- **Global Search**: Powerful search capabilities to find content based on file names, content, or comments.

## Identity & Authentication

WorkDocs requires a directory service to manage its users. It supports:
- **AWS Managed Microsoft AD**: For a native cloud directory.
- **AD Connector**: To use existing on-premises Active Directory credentials.
- **Simple AD**: For a lightweight managed directory.

## Compliance and Auditing

- **AWS CloudTrail**: Every action in WorkDocs (login, file view, deletion, sharing) is logged for auditing and security analysis.
- **HIPAA Eligible / PCI DSS Compliant**: Suitable for organizations with high compliance requirements.

---

## WorkDocs vs. WorkSpaces

- **WorkDocs**: Focused on **file storage and document collaboration**.
- **WorkSpaces**: Focused on providing a **full virtual desktop (DaaS)**.
- **Integration**: Often used together—WorkDocs can provide persistent file storage for WorkSpaces users.

---

## Exam Tips

- **AD Integration**: If an exam question asks for a secure document storage solution where employees use their **existing corporate AD credentials**, think **WorkDocs + AD Connector**.
- **Sharing**: WorkDocs supports sharing with external users via email-based invites.
- **Audit Trails**: Remember that **CloudTrail** integration is key for tracking "who accessed what" in a regulated environment.
