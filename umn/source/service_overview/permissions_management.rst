:original_name: cci_03_0008.html

.. _cci_03_0008:

Permissions Management
======================

If you need to assign different permissions to employees in your enterprise to access your CCI resources, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM provides identity authentication, permissions management, and access control, enabling secure access to your cloud resources.

With IAM, you can use your account to create IAM users, and assign permissions to the users to control their access to specific resources. For example, some software developers in your enterprise need to use CCI resources but should not be allowed to delete the resources or perform any other high-risk operations. In this scenario, you can create IAM users for the software developers and grant them only the permissions required for using CCI resources.

If your account does not require individual IAM users for permissions management, skip this section.

IAM can be used free of charge. You only pay for the resources in your account.

CCI Permissions
---------------

By default, new IAM users do not have permissions assigned. You need to add a user to one or more groups, and attach permissions policies or roles to these groups. Users inherit permissions from the groups to which they are added and can perform specified operations on cloud services based on the permissions.

CCI is a project-level service deployed and accessed in specific regions. To assign CCI permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect. If **All projects** is selected, the permissions will take effect for the user group in all region-specific projects. When accessing CCI, the users need to switch to a region where they have been authorized to use this service.

You can grant users permissions by using roles and policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. This mechanism provides only a limited number of service-level roles for authorization. When using roles to assign permissions, you need to also assign other roles on which the permissions depend to take effect. However, roles are not an ideal choice for fine-grained authorization and secure access control.
-  Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. For example, you can grant CCI users only the permissions for managing a certain type of CCI resources. Most policies define permissions based on APIs. For the API actions supported by CCI, see "Permissions Policies and Supported Actions" in the *CCI API Reference*.

:ref:`Table 1 <cci_03_0008__table1409182914134>` lists all the system-defined roles and policies supported by CCI.

.. _cci_03_0008__table1409182914134:

.. table:: **Table 1** System-defined roles and policies supported by CCI

   +----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Role/Policy Name     | Description                                                                                                                                                                                                         | Type                  |
   +======================+=====================================================================================================================================================================================================================+=======================+
   | CCI FullAccess       | Full permissions for CCI. Users granted these permissions can create, delete, query, and update all CCI resources.                                                                                                  | System-defined policy |
   +----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CCI ReadOnlyAccess   | Read-only permissions for CCI. Users granted these permissions can only view CCI resources.                                                                                                                         | System-defined policy |
   +----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CCI CommonOperations | Common user permissions for CCI. Users granted these permissions can perform all operations except creating, deleting, and modifying role-based access control (RBAC) policies, networks, and namespaced resources. | System-defined policy |
   +----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CCI Administrator    | Administrator permissions for CCI. Users granted these permissions can create, delete, query, and update all CCI resources.                                                                                         | System-defined role   |
   +----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

:ref:`Table 2 <cci_03_0008__table65762630>` lists the permissions granted by a CCI FullAccess policy.

.. _cci_03_0008__table65762630:

.. table:: **Table 2** Permissions granted by a CCI FullAccess policy

   +--------------+---------------------------------------------------------------------+
   | Action       | Description                                                         |
   +==============+=====================================================================+
   | cci:``*``:\* | Perform all operations on Cloud Container Instance (CCI).           |
   +--------------+---------------------------------------------------------------------+
   | vpc:``*``:\* | Perform all operations on Virtual Private Cloud (VPC).              |
   +--------------+---------------------------------------------------------------------+
   | elb:``*``:\* | Perform all operations on Elastic Load Balance (ELB).               |
   +--------------+---------------------------------------------------------------------+
   | sfs:``*``:\* | Perform all operations on Scalable File Service (SFS).              |
   +--------------+---------------------------------------------------------------------+
   | evs:``*``:\* | Perform all operations on Elastic Volume Service (EVS).             |
   +--------------+---------------------------------------------------------------------+
   | aom:``*``:\* | Perform all operations on Application Operations Management (AOM).  |
   +--------------+---------------------------------------------------------------------+
   | apm:``*``:\* | Perform all operations on Application Performance Management (APM). |
   +--------------+---------------------------------------------------------------------+
   | swr:``*``:\* | Perform all operations on Software Repository for Container (SWR).  |
   +--------------+---------------------------------------------------------------------+
   | nat:``*``:\* | Perform all operations on NAT Gateway.                              |
   +--------------+---------------------------------------------------------------------+
   | kms:cmk:\*   | Perform all operations on Key Management Service (KMS).             |
   +--------------+---------------------------------------------------------------------+

:ref:`Table 3 <cci_03_0008__table11562191511348>` lists the permissions granted by a CCI ReadOnlyAccess policy.

.. _cci_03_0008__table11562191511348:

.. table:: **Table 3** Permissions granted by a CCI ReadOnlyAccess policy

   =============== =============================================
   Action          Description
   =============== =============================================
   cci:``*``:get   View details about all CCI resources.
   cci:``*``:list  List all CCI resources.
   vpc:``*``:get   View details about all VPC resources.
   vpc:``*``:list  List all VPC resources.
   ecs:``*``:get   View details about all ECS resources.
   ecs:``*``:list  List all ECS resources.
   elb:``*``:get   View details about all ELB resources.
   elb:``*``:list  List all ELB resources.
   sfs:``*``:get\* View details about all SFS resources.
   sfs:``*``:list  List all SFS resources.
   evs:``*``:get\* View details about all EVS resources.
   evs:``*``:list  List all EVS resources.
   aom:``*``:get   View details about all AOM resources.
   aom:``*``:list  List all AOM resources.
   amp:``*``:get   View details about all APM resources.
   apm:``*``:list  List all APM resources.
   swr:``*``:get   View details about all SWR resources.
   swr:``*``:list  List all SWR resources.
   nat:``*``:get   View details about all NAT Gateway resources.
   nat:``*``:list  List all NAT Gateway resources.
   kms:cmk:get     Query key information.
   kms:cmk:list    List all keys.
   =============== =============================================

:ref:`Table 4 <cci_03_0008__table16111512108>` lists the permissions granted by a CCI CommonOperations policy.

.. _cci_03_0008__table16111512108:

.. table:: **Table 4** Permissions granted by a CCI CommonOperations policy

   +-----------------------------+-------------------------------------------------+
   | Action                      | Description                                     |
   +=============================+=================================================+
   | cci:rbac:get                | Query RBAC policy details.                      |
   +-----------------------------+-------------------------------------------------+
   | cci:rbac:list               | List all RBAC policies.                         |
   +-----------------------------+-------------------------------------------------+
   | cci:namespace:get           | Query namespace details.                        |
   +-----------------------------+-------------------------------------------------+
   | cci:namespace:list          | List all namespaces.                            |
   +-----------------------------+-------------------------------------------------+
   | cci:network:get             | Query network details.                          |
   +-----------------------------+-------------------------------------------------+
   | cci:network:list            | List all networks.                              |
   +-----------------------------+-------------------------------------------------+
   | cci:namespaceSubResource:\* | Perform all operations on namespaced resources. |
   +-----------------------------+-------------------------------------------------+
   | cci:addonTemplate:\*        | Perform all operations on add-on templates.     |
   +-----------------------------+-------------------------------------------------+
   | cci:addonInstance:\*        | Perform all operations on add-on pods.          |
   +-----------------------------+-------------------------------------------------+
   | vpc:``*``:\*                | Perform all operations on VPC.                  |
   +-----------------------------+-------------------------------------------------+
   | elb:``*``:\*                | Perform all operations on ELB.                  |
   +-----------------------------+-------------------------------------------------+
   | aom:``*``:\*                | Perform all operations on AOM.                  |
   +-----------------------------+-------------------------------------------------+
   | apm:``*``:\*                | Perform all operations on APM.                  |
   +-----------------------------+-------------------------------------------------+
   | swr:``*``:\*                | Perform all operations on SWR.                  |
   +-----------------------------+-------------------------------------------------+
   | nat:``*``:\*                | Perform all operations on NAT Gateway.          |
   +-----------------------------+-------------------------------------------------+
   | kms:cmk:\*                  | Perform all operations on KMS.                  |
   +-----------------------------+-------------------------------------------------+

:ref:`Table 5 <cci_03_0008__table869620272203>` lists the actions associated with CCI fine-grained policies.

.. _cci_03_0008__table869620272203:

.. table:: **Table 5** Actions associated with CCI fine-grained policies

   +---------------------------------+--------------------------------------------+
   | Action                          | Description                                |
   +=================================+============================================+
   | CCI:rbac:get                    | Query RBAC details.                        |
   +---------------------------------+--------------------------------------------+
   | CCI:rbac:list                   | List all RBAC policies.                    |
   +---------------------------------+--------------------------------------------+
   | CCI:rbac:update                 | Update RBAC policies.                      |
   +---------------------------------+--------------------------------------------+
   | CCI:rbac:delete                 | Delete RBAC policies.                      |
   +---------------------------------+--------------------------------------------+
   | CCI:rbac:create                 | Create RBAC policies.                      |
   +---------------------------------+--------------------------------------------+
   | CCI:namespaceSubResource:Create | Create resources in namespaces.            |
   +---------------------------------+--------------------------------------------+
   | CCI:namespaceSubResource:List   | List all resources.                        |
   +---------------------------------+--------------------------------------------+
   | CCI:namespaceSubResource:Get    | Query resources.                           |
   +---------------------------------+--------------------------------------------+
   | CCI:namespaceSubResource:Delete | Delete resources.                          |
   +---------------------------------+--------------------------------------------+
   | CCI:namespaceSubResource:Update | Update resources.                          |
   +---------------------------------+--------------------------------------------+
   | CCI:network:update              | Update networks.                           |
   +---------------------------------+--------------------------------------------+
   | CCI:network:create              | Create networks.                           |
   +---------------------------------+--------------------------------------------+
   | CCI:network:delete              | Delete networks.                           |
   +---------------------------------+--------------------------------------------+
   | CCI:network:list                | List all networks.                         |
   +---------------------------------+--------------------------------------------+
   | CCI:network:get                 | Query network details.                     |
   +---------------------------------+--------------------------------------------+
   | CCI:addonInstance:create        | Create add-on instances.                   |
   +---------------------------------+--------------------------------------------+
   | CCI:addonInstance:update        | Update add-on instances.                   |
   +---------------------------------+--------------------------------------------+
   | CCI:addonInstance:delete        | Delete add-on instances.                   |
   +---------------------------------+--------------------------------------------+
   | CCI:addonInstance:get           | Query add-on instance details.             |
   +---------------------------------+--------------------------------------------+
   | CCI:addonInstance:list          | List all add-on instances.                 |
   +---------------------------------+--------------------------------------------+
   | CCI:addonTemplate:list          | List all add-on templates.                 |
   +---------------------------------+--------------------------------------------+
   | CCI:addonTemplate:get           | Query add-on template details.             |
   +---------------------------------+--------------------------------------------+
   | CCI:namespace:get               | Query details about a specified namespace. |
   +---------------------------------+--------------------------------------------+
   | CCI:namespace:update            | Update namespaces.                         |
   +---------------------------------+--------------------------------------------+
   | CCI:namespace:create            | Create namespaces.                         |
   +---------------------------------+--------------------------------------------+
   | CCI:namespace:list              | List all namespaces.                       |
   +---------------------------------+--------------------------------------------+
   | CCI:namespace:delete            | Delete namespaces.                         |
   +---------------------------------+--------------------------------------------+

:ref:`Table 6 <cci_03_0008__table126113571055>` lists the common operations supported by each system-defined policy or role of CCI. Select the policies or roles as required.

.. _cci_03_0008__table126113571055:

.. table:: **Table 6** Common operations supported by each system-defined policy or role of CCI

   +----------------------------------------------+----------------+--------------------+----------------------+
   | Operation                                    | CCI FullAccess | CCI ReadOnlyAccess | CCI CommonOperations |
   +==============================================+================+====================+======================+
   | Creating Deployments                         | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting Deployments                         | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing Deployments                          | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Upgrading workloads                          | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Scaling workloads                            | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting pods                                | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing pods                                 | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Creating jobs                                | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting jobs                                | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing jobs                                 | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Creating cron jobs                           | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting cron jobs                           | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing cron jobs                            | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing the resource usage                   | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Adding EVS volumes                           | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting EVS volumes                         | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing EVS volumes                          | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Creating ConfigMaps                          | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting ConfigMaps                          | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing ConfigMaps                           | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Creating secrets                             | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting secrets                             | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing secrets                              | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Adding SSL certificates                      | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting SSL certificates                    | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing SSL certificates                     | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Adding log storage                           | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing logs                                 | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Installing add-ons                           | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting add-ons                             | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing add-ons                              | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Viewing permissions                          | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Granting permissions                         | Y              | x                  | x                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting permissions                         | Y              | x                  | x                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Querying details about a specified namespace | Y              | x                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Creating namespaces                          | Y              | x                  | x                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting namespaces                          | Y              | x                  | x                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Creating networks                            | Y              | x                  | x                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Deleting networks                            | Y              | x                  | x                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Listing all networks                         | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
   | Querying network details                     | Y              | Y                  | Y                    |
   +----------------------------------------------+----------------+--------------------+----------------------+
