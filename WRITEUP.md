### Reason for choosing App Service over VM

The cost of VM is considerably high when compared to App Service. App Service supports auto scaling while VM needs VM Scale set which is expensive. App Service has intgrated load balancer while VM needs additional load balancer. VM and App Service are available accross multiple regions.

Hence considering all of these App Service is the better approach when compared to VM for Article CMS application

### Assess app changes that would change your decision.

If the application requires software that App Service doesn't support. VM allows much customisation to the OS and security of the application. If there is need to sclae the server horizontally rather than adding additional servers.
