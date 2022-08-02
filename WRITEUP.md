### Reason for choosing App Service over VM

**Cost**

- For development we can use the App Service in free tier with 1 GB RAM
  with 1GB storage with F1 instance with no cost.
- The basic deployment with 10 GB storage, 3.5GB RAM and 4 core cost
  is $0.036/hour. Comparatively VM with 2 cores, 3.5 GB RAM and 60
  GB temp storage cost is $0.081/hour.
- The cost of App Service is substantially lower when compared to a
  VM where we need to manage the OS, patches and application
  deployment manually.

**Scalability**

- Autoscaling : Autoscaling is built in App service while VM need
  to use VM scale-set.
- Load balancing: The App service has Integrated load balancer
  where VM scale-set need additional Azure Load Balancer. Hence App service deployment for this Python based Article CMS web app is cost effective, simple yet efficient.
- Although VM supports up to 1000 nodes per scale set while App service
  only 100 (30 instances, 100 with App Service Environment), the App
  service is a better choice as the Article CMS application does not demand for such scale at this point of time

**Availability**
App Service and VM supports multi region availability except App Service is not available in all geographies
SLA for VM
|MONTHLY UPTIME PERCENTAGE| SERVICE CREDIT |
|--|--|
|< 99.99% |10% |
|< 99%|25%|
|< 95%|100%|
SLA for App Service
|MONTHLY UPTIME PERCENTAGE| SERVICE CREDIT |
|--|--|
|< 99.95% |10% |
|< 99%|25%|
|< 95%|100%|

**Workflow**

The Article CMS application is a simple web app which doesn't need full control of the VM. The application is a simple flask based application and we are leveraging the Azure SQL database the deployment is simple app server based. Also it doesn't require any specific hardware capabilities or software.

Hence considering all of these App Service is the better approach when compared to VM for Article CMS application

### Assess app changes that would change your decision.

- Many more features are added and the web app exceeds the hardware limitations of App Service .
- There is a massive increase in the number of users.
- If there is a need to increase the level of control over the underlying OS and higher security requirements.
