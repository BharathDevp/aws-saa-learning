### Architecture & tools

AWS Global infrastructure:
- 200+ IT services available
- Accessible
- Scalable
- Reliable
- Network latency
- Network security (HTTPS, VPN)
- Encryption for data at rest ex S3

AWS Region: It's an isolated environment. Each region will have 2 to 3 availability zones nothing but data centers
We can connect to AWS cloud using
- VPN from individual devices, which established encrypted tunnel to AWS cloud
Amazon data centers within region are linked using high speed fiber network of 400 Ethernet connections.

** AWS Cloud computing shared responsibility:
- Responsibility varies from one service to another (IaaS, PaaS, SaaS)
- IaaS
  - Customers manually deploys services like EC2 instances, S3 buckets etc
  - For VMs, customer is responsible for it's OS, configurations, Apps, patching etc
  - For VMs, Amazon is responsible for underlying hardware and hypervisors
- PaaS (Server less computing)
  - Customer deploys managed platform such as Relational Database service (RDS)
  - Customer is responsible for limited configuration settings and all data
  - Amazon manages underlying infrastructure and underlying services such as EC2 instances
  - Customer won't be having direct access to the underlying infra to configure or manage
- SaaS
  - One is customer can develop there own software and deploy in cloud. AWS will take care of underlying infra and manages
  - Other way is to use SaaS offerings available in cloud like cloud based mail etc...
  - *TODO*: Difference between PaaS and SaaS
 
# AWS well architected framework:
- It follows Six pillar design principles set to deliver services to end user
  - Operation excellence
  - Security
  - Reliability
  - Performance efficiency
  - Cost optimization
  - Sustainability

 1. Operation Excellence:
    - Its all about monitoring the deployed services to ensure peak efficiency and utilization.
    - It's done using analysing performance metrics through CloudWatch
 2. Security:
    - It takes care of data confidentiality so that only authorized services or users only can access data. This ensures encryption both over the network and data at rest. For example, S3 buckets are by default encrypted by Amazon server side keys
    - Data integrity 
    - IAM users, roles, policies, threat protection
3. Reliability:
   - Distributed system design: regions, AZs, replication
   - Disaster recovery plan for each and every service
   - Ability to change as need evolve like scale out, scale in, scale up or down
4. Performance efficiency:
   - Match service sizing to workload requirements
   - monitor performance metrics and adjust sizing accordingly
5. Cost Optimization:
   - Remove unused resource or atleast shutdown them

# AWS Service Matching:

- Business needs assessment
- Familiarity with AWS service offerings
- Network requirements: Assess each one of below while designing application
  - VPCs, Subnets: Assessing how many VPCs and Subnets required for our application
  - VPC peering: to allow direct VPC to VPC communication instead of communicate over public network
  - VPN: To access AWS cloud over encrypted tunnel from outside world
  - Direct connect: Direct communication channel to talk to AWS cloud
  - HTTPS: To talk to service endpoints hosted on AWS
  - Network/Threat monitoring: GaurdDuty, CloudWatch network metrics to make sure everything working as expected
- Compute requirements
  - EC2 instances: Decide if we need to deploy EC2 instances manually, which requires us to setup full configuration. We need to take care of config updates, patches etc...
  - Managed services: Paas services like AWS Lambda, which will have limited indirect VM configuration.
  - Application containers: Elastic container service(ECS), Elastic container registry(ECR)
  - Container clusters: Elastic kubernetes service
- Storage requirements
  - S3 bucket object storage: to store files, objects etc. By default comes with encryption
  - Databases: NoSQL or SQL based on the requirement
  - Security: Amazon Macie data classification, server side encryption with Amazon keys or customer managed keys
- Monitoring and Security requirements: Continuous monitoring of the services deployed is utmost important.
  - CloudWatch monitoring: to monitor deployed cloud services and take actions like increase/decrease resources, scale up or scale out etc
  - CloudTrail auditing: helps to audit any unwanted actions performed etc...
  - Amazon detective: It helps to identify potential security incidents and to investigate them
  - Network ACLs: to control the traffic in and out of network VPCs
  - Security groups: to control the traffic in and out of EC2 instances
  - Web application Firewall (WAF): To protect web app from security threats like SQL injection etc...
  - Security standards compliance: PCI DSS, GDPR compliance etc...
- AWS service sprawl reduction - Remove unused resources those are running in background

# Summary of Course:
- AWS global infrastructure, shared responsibility models, pillars of well-architected framework and service fits
- AWS CLI on Windows and Linux
- Amazon Linux and the CLI, Powershell tools, Cloudshell, and AWS Outposts
