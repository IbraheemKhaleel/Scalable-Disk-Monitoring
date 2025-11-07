# AWS Scalable Disk Monitoring (Ansible + CloudWatch + SSM)

# Please read the file : Solution Implementation with Architecture.txt provided in the repo for detailed architecture and explanation

This repository implements a scalable disk utilization monitoring solution for EC2 instances across multiple AWS accounts using **Ansible**, **CloudWatch**, and **SSM**.

## Setup
1. Configure cross-account IAM roles and OAM link.
2. Tag instances with `Monitoring=Enabled`.
3. Update `group_vars/all.yml` for your SNS ARN and regions.
4. Run:
   ```bash
   ansible-playbook playbooks/setup-cwagent.yml
   ansible-playbook playbooks/create-alarms.yml
   ansible-playbook playbooks/create-dashboard.yml
   ```

## Features
- Cross-account secure management (via SSM)
- Auto-discovery via tags
- CloudWatch dashboards and alarms
- Scales with fleet growth

