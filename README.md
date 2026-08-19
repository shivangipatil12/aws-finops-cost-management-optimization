# 🚀 AWS FinOps Cost Management & Optimization

## 📌 Project Overview

A small business runs a web application on AWS and wants better visibility, control, and optimization of its cloud spending.

This project demonstrates how FinOps practices can be applied to an AWS environment to monitor resource usage, analyze costs, establish cost controls, apply cost allocation, and identify optimization opportunities.

## 🎯 Project Objectives

- Secure AWS resources
- Create a basic AWS workload
- Monitor resource utilization
- Track AWS costs
- Establish cost controls
- Apply cost allocation tags
- Identify optimization opportunities
- Document FinOps recommendations

## ☁️ AWS Services Used

| Category | AWS Service | Purpose |
|---|---|---|
| Compute | Amazon EC2 | Run the project workload |
| Storage | Amazon S3 | Store project files and documentation |
| Identity & Security | AWS IAM | Control access |
| Monitoring | Amazon CloudWatch | Monitor EC2 resource utilization |
| Cost Analysis | AWS Cost Explorer | Analyze AWS spending |
| Cost Control | AWS Budgets | Set spending alerts |
| Cost Allocation | AWS Tags | Identify and allocate resource costs |

## 🏗️ Architecture

The project uses a conceptual AWS architecture consisting of EC2, S3, IAM, CloudWatch, Cost Explorer, AWS Budgets, and cost allocation tags.

The project focuses on AWS cost management and monitoring rather than deploying a production web application.

## 🖥️ EC2 Configuration

- AMI: Amazon Linux 2023
- Instance type: `t3.micro`
- vCPU: 2
- Memory: 1 GiB
- Storage: 8 GiB encrypted gp3 EBS volume
- SSH access: Restricted to My IP
- Security Group: `finops-project-sg`

## 📊 Monitoring

CloudWatch monitors the EC2 instance's CPU utilization.

**Alarm:**
- Name: `finops-project-ec2-high-cpu`
- Metric: `CPUUtilization`
- Threshold: ≥ 70%
- Evaluation: 1 datapoint within 5 minutes
- Current state: OK

Observed CPU utilization was approximately **0.107%–0.213%** during the analysis period.

## 💰 Cost Management

### Cost Explorer

Cost Explorer was used to analyze AWS spending.

- Analysis period: Last 7 days
- Granularity: Daily
- Group by: Service
- Observed billable cost: $0

The `Project = AWS-FinOps` tag was also analyzed, with observed project cost of $0.

### AWS Budget

- Budget: `$1` monthly
- Actual cost: `$0`
- Alert threshold: Actual cost > `$0.01`
- Status: OK / Healthy
- Automated actions: None

### Cost Allocation Tags

The following cost allocation tags were activated:

| Tag | Value |
|---|---|
| Project | `AWS-FinOps` |
| Environment | `Learning` |
| Application | `FinOps-Demo` |

## 🔍 FinOps Analysis

### EC2

Current CPU utilization is very low. However, the instance was recently started, so there is insufficient historical data to make a reliable rightsizing decision.

**Recommendation:** Continue monitoring CPU utilization over a longer period before changing the instance type.

### EBS

The EC2 instance uses a single 8 GiB encrypted EBS root volume. No immediate storage optimization opportunity was identified.

### S3

The project bucket contains one 22.4 KB object in S3 Standard. The storage footprint is minimal, so no immediate storage-class optimization is justified.

### Overall Findings

- Cost visibility established through Cost Explorer
- Cost allocation established through tagging
- Spending control established through AWS Budgets
- Resource monitoring established through CloudWatch
- EC2 utilization analyzed
- EBS and S3 storage analyzed
- FinOps optimization opportunities identified

## 💡 FinOps Recommendations

1. Continue monitoring EC2 utilization before rightsizing.
2. Stop EC2 when it is not required to avoid unnecessary compute charges.
3. Keep EBS storage minimal and remove unused resources.
4. Review S3 storage periodically and consider lifecycle policies as data grows.
5. Maintain consistent resource tagging.
6. Continue monitoring Cost Explorer and AWS Budget alerts.
7. Periodically review AWS resources for unused or underutilized resources.

## 📁 Project Documentation

Detailed project documentation, architecture diagrams, and AWS console screenshots will be added to this repository.

## 🎯 Project Outcome

This project demonstrates practical application of FinOps principles across AWS infrastructure, including cost visibility, monitoring, budgeting, cost allocation, resource analysis, and optimization recommendations.
