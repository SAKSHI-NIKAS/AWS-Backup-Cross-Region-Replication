# AWS Backup Cross-Region Replication for EC2

## Overview

This project demonstrates how to configure **AWS Backup** to automatically protect an Amazon EC2 instance and replicate recovery points to another AWS Region for disaster recovery. The implementation ensures that backups are securely stored in both the primary and secondary regions, improving data durability and business continuity.

---

## Project Objectives

- Configure automated backups for an Amazon EC2 instance.
- Create backup vaults in multiple AWS Regions.
- Implement cross-region backup replication.
- Validate backup and copy jobs.
- Verify recovery points in both source and destination regions.

---

## Architecture

```
               +-------------------------+
               |      Amazon EC2         |
               |   (N. Virginia)         |
               +-----------+-------------+
                           |
                           |
                    AWS Backup Plan
                           |
                           |
               +-----------v-------------+
               |  PrimaryBackupVault     |
               |   (N. Virginia)         |
               +-----------+-------------+
                           |
               Cross-Region Copy Rule
                           |
                           |
               +-----------v-------------+
               |    DRBackupVault        |
               |      (Ohio)             |
               +-------------------------+
```

---

## AWS Services Used

- Amazon EC2
- AWS Backup
- Backup Vault
- AWS Identity and Access Management (IAM)
- Amazon EBS

---

## Implementation Steps

### 1. Launch an EC2 Instance
- Created an EC2 instance in **US East (N. Virginia)**.
- Added sample data to validate backup integrity.

### 2. Create Backup Vaults
- **PrimaryBackupVault** in N. Virginia.
- **DRBackupVault** in Ohio.

### 3. Configure AWS Backup Plan
- Created a daily backup plan.
- Configured a retention period of **35 days**.
- Assigned the EC2 instance to the backup plan.

### 4. Enable Cross-Region Replication
- Configured a copy rule.
- Destination Region: **US East (Ohio)**.
- Destination Vault: **DRBackupVault**.

### 5. Validate Backup
- Executed an on-demand backup.
- Verified successful backup completion.
- Confirmed recovery points in both backup vaults.

---

## Project Outcome

- Successfully configured automated EC2 backups.
- Implemented cross-region backup replication.
- Verified backup recovery points in both AWS Regions.
- Demonstrated disaster recovery using AWS Backup.

---

## Challenges Faced

- Resolved IAM permission issues during backup execution.
- Correctly configured EC2 resource assignment.
- Validated cross-region backup replication.

---

## Screenshots

- EC2 Instance
- Backup Plan
- Resource Assignment
- Primary Backup Vault
- Backup Job (Completed)
- Copy Job (Completed)
- DR Backup Vault (Ohio)
- Recovery Point Verification

---

## Skills Demonstrated

- AWS Backup
- Amazon EC2
- Disaster Recovery
- Cross-Region Replication
- IAM
- Cloud Infrastructure
- Backup & Recovery

---

## Author

**Sakshi Nikas**
