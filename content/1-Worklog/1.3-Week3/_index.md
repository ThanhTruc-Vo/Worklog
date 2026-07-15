---
title: "Worklog Week 3"
date: 2026-05-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:
- Study NAT Gateway and Internet connectivity mechanisms for Private Subnets.
- Practice using EC2 Instance Connect Endpoint (EICE).
- Research secure connection methods in AWS.
- Learn about AWS cost optimization and resource cleanup procedures.
### Tasks to Deploy This Week:

| Day | Task                                                                                                                                         | Start Date | Completion Date | Reference                                                              |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------- |
| 2   | - Study NAT Gateway concepts <br> - Learn Internet access mechanisms for Private Subnets                                                     | 04/05/2026 | 04/05/2026      | [https://000003.awsstudygroup.com/](https://000003.awsstudygroup.com/) |
| 3   | - Study Route Tables and VPC routing mechanisms <br> - Research EC2 Instance Connect Endpoint (EICE)                                         | 05/05/2026 | 05/05/2026      | [https://000003.awsstudygroup.com/](https://000003.awsstudygroup.com/) |
| 4   | - Study Security Groups for EICE <br> - Research SSH Connection Troubleshooting                                                              | 06/05/2026 | 06/05/2026      | [https://000003.awsstudygroup.com/](https://000003.awsstudygroup.com/) |
| 5   | - Practice deploying NAT Gateway and EICE <br> - Test Internet connectivity from EC2 Private <br> - Connect to EC2 Private using AWS Console | 07/05/2026 | 07/05/2026      | [https://000003.awsstudygroup.com/](https://000003.awsstudygroup.com/) |
| 6   | - Research and propose personal project ideas <br> - Prepare project proposal presentation materials                                         | 08/05/2026 | 08/05/2026      | Internal Research                                                      |
| 7   | - Discuss and select the most suitable project topic for the team                                                                            | 09/05/2026 | 09/05/2026      | Internal Meeting                                                       |


### Week 3 Achievements:

| Day | Task                                          | Achievements                                                                                                                                                                                                                                                       |
| --- | --------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | NAT Gateway Research                          | Understood how NAT Gateway works and how Internet access is provided to Private Subnets through Elastic IP and Route Tables.                                                                                                                                                           |
| 3   | EC2 Instance Connect Endpoint (EICE) Research | Understood the architecture and operation of EC2 Instance Connect Endpoint, enabling secure access to private EC2 instances without Public IPs or Bastion Hosts.                                                                                                                       |
| 4   | Security Group and Troubleshooting Research   | Learned how to configure Security Groups for EICE, troubleshoot SSH connection issues, and perform network troubleshooting in AWS Cloud environments.                                                                                                                                  |
| 5   | NAT Gateway and EICE Lab Practice             | Successfully implemented NAT Gateway, Route Table, Security Group, and EC2 Instance Connect Endpoint. Successfully connected to EC2 Private instances directly from the AWS Console. Performed resource cleanup immediately after completing the lab to avoid unnecessary AWS charges. |
| 6   | Personal Project Proposal                     | Completed the preparation of personal project proposals based on the Cloud/AI orientation of the FCAJ program.                                                                                                                                                                         |
| 7   | Project Topic Discussion                      | Participated in team discussions, evaluated project ideas, and selected the final project topic for implementation.                                                                                                                                                                    |

### Practical Evidence Images:

#### 1. Establishing an SSH connection to the public server (EC2-Public) via MobaXterm

Successfully connected to the public server instance at IP `34.239.227.34` running Amazon Linux 2023 using the MobaXterm client SSH session.
![Establishing an SSH connection to EC2 Public via MobaXterm](/images/1-Worklog/1.3-Week3/image-1.png)

#### 2. Checking Internet connectivity and executing API calls from the Public instance

Executed a successful `ping` command to test public wide-area network routing to Google and leveraged `curl -I` to verify valid HTTP header responses from Amazon.
![Checking network connectivity from the Public instance](/images/1-Worklog/1.3-Week3/image-2.png)

#### 3. Configuring key pair permissions and performing a multi-hop SSH connection from Public to Private

Configured secure access permissions for the private key file (`chmod 400`) and initiated a protected internal SSH connection from the public subnet space into the private server instance (`10.0.2.157`).
![SSH from Public instance to Private instance](/images/1-Worklog/1.3-Week3/image-3.png)

#### 4. Allocating a static public IP (Elastic IP) for the NAT Gateway infrastructure

The VPC management dashboard indicates successful allocation of a dedicated static Elastic IP `32.194.27.77` designated as `EIP-NAT-AZ1a` to back the gateway network routing.
![Allocating an Elastic IP](/images/1-Worklog/1.3-Week3/image-4.png)

#### 5. Launching the NAT Gateway resource within the AWS Management Console

The networking engine records that the `NAT-Gateway-AZ1a` service has been properly mapped to the newly provisioned static Elastic IP and has fully transitioned into the active `Available` state.
![Launching the NAT Gateway](/images/1-Worklog/1.3-Week3/image-5.png)

#### 6. Verifying one-way outbound network communication from the isolated Private server

Following proper route table updates through the NAT Gateway, the isolated `EC2-Private` host successfully executed a `ping 8.8.8.8` request, receiving complete external data packets.
![Testing network routing from Private instance via NAT Gateway](/images/1-Worklog/1.3-Week3/image-6.png)

#### 7. Direct terminal administration utilizing the EC2 Instance Connect Endpoint (EICE) service

Established an authenticated secure console session straight into the private environment terminal from a standard web browser interface via the designated endpoint attachment.
![Access via EC2 Instance Connect Endpoint](/images/1-Worklog/1.3-Week3/image-7.png)
