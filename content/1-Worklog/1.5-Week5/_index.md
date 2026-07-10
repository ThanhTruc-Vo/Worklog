---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

- Study advanced Amazon EC2 architecture and instance types.
- Learn AWS storage and backup services.
- Practice deploying AWS Backup and performing data recovery.
- Prepare for Amazon S3 Advanced Features in upcoming labs.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study Amazon EC2 Instance Types <br> - Learn Intel, AMD, and AWS Graviton CPU architectures | 05/18/2026 | 05/18/2026 | AWS Skill Builder / AWS Documentation |
| 3 | - Learn Amazon EBS Volumes and Instance Store <br> - Study EC2 User Data and Instance Metadata | 05/19/2026 | 05/19/2026 | AWS Skill Builder / AWS Documentation |
| 4 | - Study Auto Scaling and Elastic Load Balancing <br> - Learn Amazon EFS and Amazon FSx | 05/20/2026 | 05/20/2026 | AWS Skill Builder / AWS Documentation |
| 5 | - Practice Lab 13: Deploy AWS Backup to the System <br> - Create Backup Plan, Backup Vault, and perform Restore Test | 05/21/2026 | 05/21/2026 | First Cloud AI Journey Course |
| 6 | - Study Amazon S3 Advanced Features <br> - Learn Static Website Hosting, Versioning, CloudFront, and Cross-Region Replication | 05/22/2026 | 05/22/2026 | Amazon S3 Documentation |
| 7 | - Attend the **AWS First Cloud AI Journey Community Day** <br> - Participate in technical sessions and networking activities with the AWS community | 05/23/2026 | 05/23/2026 | AWS First Cloud AI Journey Community |

### Week 5 Achievements:

| Day | Task | Achievement |
| --- | --- | --- |
| 2 | Study Amazon EC2 | Gained an understanding of Amazon EC2 Instance Types, Intel, AMD, and AWS Graviton processor architectures, and learned how to select suitable instances for different workloads. |
| 3 | Learn EC2 Storage | Understood the differences between Amazon EBS Volumes and Instance Store, and learned how EC2 User Data and Instance Metadata are used during instance initialization. |
| 4 | Study Auto Scaling and Storage Services | Learned how Auto Scaling and Elastic Load Balancing improve application availability and scalability, and gained basic knowledge of Amazon EFS and Amazon FSx. |
| 5 | Deploy AWS Backup | Successfully created an AWS Backup Plan, Backup Vault, and performed a Restore Test, gaining practical experience with backup and disaster recovery on AWS. |
| 6 | Study Amazon S3 Advanced Features | Acquired foundational knowledge of Static Website Hosting, CloudFront, Versioning, and Cross-Region Replication in Amazon S3 for upcoming labs. |
| 7 | Attend Community Day | Participated in the AWS First Cloud AI Journey Community Day, gained practical insights from AWS experts, learned real-world cloud implementation experiences, and expanded professional networking within the AWS community. |

### Practical Proof Images of the Lab:

#### 1. Initialize Lab 20 Network Infrastructure via CloudFormation

The system reports the successful deployment of the Lab20-Stack, automatically creating 4 VPC networks and accompanying EC2 servers for the Transit Gateway lab.
![alt text](image.png)

#### 2. Initialize the Central Router AWS Transit Gateway

The interface shows the central connection gateway lab20-tgw has been successfully initialized and is in the Available state.
![alt text](image-1.png)

#### 3. Configure Network Links (Transit Gateway Attachments)

Successfully attached all 4 independent VPC networks to the Transit Gateway, forming a Hub-and-Spoke centralized network model.
![alt text](image-2.png)

#### 4. Configure TGW Route Table - Associations Tab

The Transit Gateway route table records the successfully Associated VPCs, ready for routing.
![alt text](image-6.png)

#### 5. Configure TGW Route Table - Propagations Tab

Successfully activated the automatic route Propagation feature, allowing the Transit Gateway to automatically recognize the IP ranges of the 4 connected VPC networks.
![alt text](image-7.png)

#### 6. Update Route Tables at the VPCs

Network routing at the VPCs has been fine-tuned, establishing a path for the 172.16.0.0/16 IP range pointing directly to the Transit Gateway instead of the Internet.
![alt text](image-8.png)

#### 7. SSH into the Bastion Host Server (VPC 1)

Successfully used MobaXterm to access the EC2 server located in VPC 1 (IP 100.48.207.178) as a jump host (Bastion Host) in preparation for network testing.
![alt text](image-3.png)

#### 8. Check Internet Connection from the Bastion Server

Successfully executed the ping amazon.com and ping google.com commands from the VPC 1 server to ensure the server has a stable external network connection before testing the internal network.
![alt text](image-7.png)

#### 9. Execute the ping 172.16.2.5 command (VPC 2). Although the ping failed (100% packet loss) due to the Security Group not allowing ICMP, network routing is clear

From the Bastion server in VPC 1, execute the ping command to 172.16.2.5 (VPC 2). The successful response data proves the central network has routed seamlessly.
![alt text](image-4.png)

#### 10. Cross-SSH to VPC 2 and Continue Testing to VPC 3

Used the key file (tgw-key.pem) to SSH directly from the jump host in VPC 1 to the Private IP of the server in VPC 2 (172.16.2.5). Immediately after, successfully executed a ping command to the IP range of VPC 3 (172.16.3.7).
![alt text](image-9.png)

#### 11. Complete Comprehensive Routing Check (VPC 4)

Continued the Transit Gateway central network testing flow by successfully pinging from the current server to the IP range of VPC 4 (172.16.4.6). The network system of all 4 VPCs is completely and securely interconnected.
![alt text](image-10.png)
