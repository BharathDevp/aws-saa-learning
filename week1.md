* Day 1: Architecture & tools

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
   

