⚠️ This repository is for learning purposes only.  
Do not attempt to apply these modules to a live AWS environment unless explicitly authorized.

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

---

## 🔒 Security Best Practices

- **Never** commit AWS credentials, secrets, or `.tfstate` files. See [.gitignore](.gitignore).
- Use IAM roles with least privilege for Terraform operations. Example policies are provided in each module (coming soon).
- Review all modules before applying them in production.
- Enable MFA on your AWS accounts.
- See [SECURITY.md](SECURITY.md) for more.

---

## 📚 Learning Resources

### Terraform
- [Official Tutorials](https://developer.hashicorp.com/terraform/tutorials)
- [FreeCodeCamp Beginner Guide](https://www.freecodecamp.org/news/terraform-beginner-tutorial/)
- [AWS Provider Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)

### AWS Cost Optimization
- [AWS Cost Optimization Pillar](https://wa.aws.amazon.com/wat.pillar.costOptimization.en.html)
- [AWS Free Tier & Budgets](https://aws.amazon.com/free/)
- [AWS Compute Optimizer](https://aws.amazon.com/compute-optimizer/)
- [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/)
- [FinOps Foundation](https://www.finops.org/introduction/what-is-finops/)

---

## 🛠️ Plug-and-Play Usage

Anyone with valid AWS credentials can use this repo:

1. **Clone or fork the repo:**
   ```bash
   git clone https://github.com/your-username/aws-cost-optimizer.git
   cd aws-cost-optimizer
   ```
2. **Configure AWS credentials:**
   ```bash
   aws configure
   ```
3. **Initialize Terraform:**
   ```bash
   terraform init
   ```
4. **Apply a module:**
   ```bash
   cd modules/ec2-scheduler
   terraform apply
   ```

- Each module is independent and reusable.
- Provide your own `terraform.tfvars` as needed.
- See [LICENSE](LICENSE) for usage rights.

---

## 🛡️ Required IAM Permissions (Example)

Each module may require different AWS permissions. Below is a sample policy for running the EC2 Scheduler module:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances",
        "ec2:StartInstances",
        "ec2:StopInstances",
        "cloudwatch:PutMetricAlarm",
        "events:PutRule",
        "events:PutTargets",
        "iam:PassRole"
      ],
      "Resource": "*"
    }
  ]
}
```

- See each module for more specific permissions.

---
