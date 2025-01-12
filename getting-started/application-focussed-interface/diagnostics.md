# Diagnostics

The DuploCloud platform automatically orchestrates three main diagnostic functions:

* **Central Logging:** A shared Elasticsearch cluster is deployed and file beat is installed in all worker nodes to fetch the logs from various applications across tenants. The logs are injected with metadata corresponding to Tenant name, service name, container ID, Host name, etc. Further, each tenant has the central logging dashboard which includes the Kibana view of the logs from applications within the service. See the screenshot below:

![](<../../.gitbook/assets/Screen Shot 2022-03-12 at 8.23.48 PM.png>)

* **Metrics**: Metrics are fetched from hosts, containers and cloud services like ELB, RDS, Redis, etc., and displayed in Grafana. Behind the scenes, for cloud services these are collected by calling cloud provider APIs like CloudWatch and Azure Mon, while for nodes and containers this is done using Prometheus, Node exporter and cAdvisor. Again, the dashboards are Tenant centric segregated per application and per cloud service as shown in the picture below:

![](<../../.gitbook/assets/Screen Shot 2022-03-12 at 8.29.48 PM.png>)

* **Alarms and Faults**: The platform creates faults for many failures automatically, such as Health check, container crashes, node crashes, deployment failures, etc. Further, users can easily set alarms on cloud services like CPU and Memory on EC2 instances, Free Disk space in RDS database, etc. All failures are displayed as faults per tenant. Sentry and Pager Duty projects can be linked to each tenant and DuploCloud will send these faults there so the user can set notification configurations.
* **Audit Trail:** An audit trail of all changes made to the system are logged in Elasticsearch where these can be audited using high level constructs like changes by tenant, by service, by change type, by user and dozens of other such filters.

![](<../../.gitbook/assets/Screen Shot 2022-03-12 at 8.37.47 PM.png>)
