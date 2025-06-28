# 🌍 AWS Cost Optimization with Terraform

**Optimize your AWS cloud spend using Terraform and free AWS-native tools.**  
This repository provides Infrastructure as Code (IaC) modules to identify, manage, and reduce unnecessary AWS expenses, using automation and FinOps best practices.

---

## 📦 Modules Included

| Module                    | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| `ec2-scheduler`           | Automatically start/stop EC2 instances based on a schedule to reduce idle time. |
| `s3-lifecycle`            | Apply intelligent lifecycle rules to move data to cheaper storage tiers.       |
| `budget-alerts`           | Set budget limits and alert you when usage exceeds thresholds.                |
| `unused-ebs-cleanup`      | Identify and optionally delete unattached EBS volumes.                        |
| `right-sizing-advisor`    | Suggest EC2 instance rightsizing using AWS Compute Optimizer.                 |
| `tag-enforcement`         | Enforce cost allocation tags using AWS Config rules and SCP policies.         |

---

## 🚀 Quick Start

### Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) ≥ 1.0
- AWS CLI configured (`aws configure`)
- An AWS account with the necessary permissions

### Deployment

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/aws-cost-optimizer.git
   cd aws-cost-optimizer

2. Initialize Terraform:
   ```bash
    terraform init
3. Apply the desired module (e.g., EC2 Scheduler):
   ```bash
   cd modules/ec2-scheduler
   terraform apply
