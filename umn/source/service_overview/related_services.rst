:original_name: cci_03_0006.html

.. _cci_03_0006:

Related Services
================

CCI needs to be interconnected with the following cloud services. It requires permissions to access these cloud services.

-  **SWR**

   SoftWare Repository for Container (SWR) provides easy, secure, and reliable management of container images throughout their lifecycles, facilitating quick deployment of containerized services.

   You can create workloads using SWR images.

-  **VPC**

   Virtual Private Cloud (VPC) allows you to isolate online resources with virtual private networks. You can configure the CIDR block, subnets, and security groups, assign EIPs, and allocate bandwidth for a VPC.

   When creating a namespace, you must associate it with a VPC. All containers to be created in the namespace will run in the VPC.

-  **ELB**

   Elastic Load Balance (ELB) automatically distributes access traffic to multiple Elastic Cloud Servers (ECSs) to balance the loads. It enhances an application's fault tolerance level and capabilities of providing service externally.

   You can access a container workload from an external network through an elastic load balancer.

-  **AOM**

   Application Operations Management (AOM) is a one-stop platform for O&M personnel to monitor application and resource operating statuses in real time. By analyzing dozens of metrics, alarms, and logs, you can quickly locate root causes to ensure services run normally.

   AOM collects the .log files of containers from CCI to facilitate log query and viewing. In addition, AOM provides resource monitoring to enable CCI to automatically scale resources.

-  **ECS**

   Elastic Cloud Server (ECS) allows you to create cloud servers that provide scalable, on-demand computing resources for secure, flexible, and efficient applications.

   CCI imports data to SFS through ECS for container services to use.

-  **NAT Gateway**

   NAT Gateway provides source network address translation (SNAT), which translates private IP addresses to public IP addresses by binding an elastic IP address (EIP) to the gateway.

   You can use NAT Gateway to set SNAT rules to allow containers in a VPC to access the Internet.
