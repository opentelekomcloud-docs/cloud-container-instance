:original_name: cci_02_0083.html

.. _cci_02_0083:

Category of CCI Actions
=======================

.. _cci_02_0083__table6129054123319:

.. table:: **Table 1** Namespace management actions

   +----------------------+---------------------------------------+----------------------+-------------+--------------------+
   | Permissions          | API                                   | Action               | IAM Project | Enterprise Project |
   +======================+=======================================+======================+=============+====================+
   | Creating a Namespace | POST /apis/cci/v2/namespaces          | CCI:namespace:create | Y           | Y                  |
   +----------------------+---------------------------------------+----------------------+-------------+--------------------+
   | Reading a Namespace  | GET /apis/cci/v2/namespaces/{name}    | CCI:namespace:get    | Y           | Y                  |
   +----------------------+---------------------------------------+----------------------+-------------+--------------------+
   | Listing Namespaces   | GET /apis/cci/v2/namespaces           | CCI:namespace:list   | Y           | Y                  |
   +----------------------+---------------------------------------+----------------------+-------------+--------------------+
   | Deleting a Namespace | DELETE /apis/cci/v2/namespaces/{name} | CCI:namespace:delete | Y           | Y                  |
   +----------------------+---------------------------------------+----------------------+-------------+--------------------+

.. _cci_02_0083__table529334703410:

.. table:: **Table 2** Pod management actions

   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Permissions                                  | API                                                     | Action                          | IAM Project | Enterprise Project |
   +==============================================+=========================================================+=================================+=============+====================+
   | Creating a Pod                               | POST /apis/cci/v2/namespaces/{namespace}/pods           | CCI:namespaceSubResource:Create | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Reading a Pod                                | GET /apis/cci/v2/namespaces/{namespace}/pods/{name}     | CCI:namespaceSubResource:Get    | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Reading All Pods Under a Specified Namespace | GET /apis/cci/v2/namespaces/{namespace}/pods            | CCI:namespaceSubResource:List   | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Reading Pod Logs                             | GET /apis/cci/v2/namespaces/{namespace}/pods/{name}/log | CCI:namespaceSubResource:Get    | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Listing All Pods of a User                   | GET /apis/cci/v2/pods                                   | cci:namespaceSubResource:List   | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Replacing a Pod                              | PUT /apis/cci/v2/namespaces/{namespace}/pods/{name}     | CCI:namespaceSubResource:Update | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Updating a Pod                               | PATCH /apis/cci/v2/namespaces/{namespace}/pods/{name}   | CCI:namespaceSubResource:Update | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Deleting a Pod                               | DELETE /apis/cci/v2/namespaces/{namespace}/pods/{name}  | CCI:namespaceSubResource:Delete | Y           | Y                  |
   +----------------------------------------------+---------------------------------------------------------+---------------------------------+-------------+--------------------+

.. _cci_02_0083__table19741529184014:

.. table:: **Table 3** Network management actions

   +---------------------+----------------------------------------------------------------+-------------------------------+-------------+--------------------+
   | Permissions         | API                                                            | Action                        | IAM Project | Enterprise Project |
   +=====================+================================================================+===============================+=============+====================+
   | Creating a Network  | POST /apis/yangtse/v2/namespaces/{namespace}/networks          | -  CCI:network:Create         | Y           | Y                  |
   |                     |                                                                | -  vpc:vpcs:create            |             |                    |
   |                     |                                                                | -  vpc:ports:create           |             |                    |
   |                     |                                                                | -  vpc:vpcs:get               |             |                    |
   |                     |                                                                | -  vpc:subnets:get            |             |                    |
   |                     |                                                                | -  vpc:publicIps:get          |             |                    |
   |                     |                                                                | -  vpc:bandwidths:get         |             |                    |
   |                     |                                                                | -  vpc:ports:get              |             |                    |
   |                     |                                                                | -  vpc:peerings:get           |             |                    |
   |                     |                                                                | -  vpc:quotas:list            |             |                    |
   |                     |                                                                | -  vpc:privateIps:get         |             |                    |
   |                     |                                                                | -  vpc:securityGroups:get     |             |                    |
   |                     |                                                                | -  vpc:securityGroupRules:get |             |                    |
   |                     |                                                                | -  vpc:networks:get           |             |                    |
   |                     |                                                                | -  vpc:routers:get            |             |                    |
   |                     |                                                                | -  vpc:floatingIps:get        |             |                    |
   |                     |                                                                | -  vpc:firewallRules:get      |             |                    |
   +---------------------+----------------------------------------------------------------+-------------------------------+-------------+--------------------+
   | Reading a Network   | GET /apis/yangtse/v2/namespaces/{namespace}/networks/{name}    | CCI:network:Get               | Y           | Y                  |
   +---------------------+----------------------------------------------------------------+-------------------------------+-------------+--------------------+
   | Listing Networks    | GET /apis/yangtse/v2/namespaces/{namespace}/networks           | CCI:network:List              | Y           | Y                  |
   +---------------------+----------------------------------------------------------------+-------------------------------+-------------+--------------------+
   | Deleting a Network  | DELETE /apis/yangtse/v2/namespaces/{namespace}/networks/{name} | -  CCI:network:Delete         | Y           | Y                  |
   |                     |                                                                | -  vpc:vpcs:delete            |             |                    |
   |                     |                                                                | -  vpc:ports:delete           |             |                    |
   +---------------------+----------------------------------------------------------------+-------------------------------+-------------+--------------------+
   | Replacing a network | PUT                                                            | -  CCI:network:Update         | Y           | Y                  |
   |                     |                                                                | -  vpc:vpcs:update            |             |                    |
   |                     | /apis/yangtse/v2/namespaces/{namespace}/network                | -  vpc:ports:update           |             |                    |
   +---------------------+----------------------------------------------------------------+-------------------------------+-------------+--------------------+

.. _cci_02_0083__table833064864119:

.. table:: **Table 4** ConfigMap management actions

   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Permissions           | API                                                          | Action                          | IAM Project | Enterprise Project |
   +=======================+==============================================================+=================================+=============+====================+
   | Creating a ConfigMap  | POST /apis/cci/v2/namespaces/{namespace}/configmaps          | CCI:namespaceSubResource:Create | Y           | Y                  |
   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Reading a ConfigMap   | GET /apis/cci/v2/namespaces/{namespace}/configmaps/{name}    | CCI:namespaceSubResource:Get    | Y           | Y                  |
   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Listing ConfigMaps    | GET /apis/cci/v2/namespaces/{namespace}/configmaps           | CCI:namespaceSubResource:List   | Y           | Y                  |
   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Replacing a ConfigMap | PUT /apis/cci/v2/namespaces/{namespace}/configmaps/{name}    | CCI:namespaceSubResource:Update | Y           | Y                  |
   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Updating a ConfigMap  | PATCH /apis/cci/v2/namespaces/{namespace}/configmaps/{name}  | CCI:namespaceSubResource:Update | Y           | Y                  |
   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Deleting a ConfigMap  | DELETE /apis/cci/v2/namespaces/{namespace}/configmaps/{name} | CCI:namespaceSubResource:Delete | Y           | Y                  |
   +-----------------------+--------------------------------------------------------------+---------------------------------+-------------+--------------------+

.. _cci_02_0083__table16668191964212:

.. table:: **Table 5** Secret management actions

   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Permissions         | API                                                       | Action                          | IAM Project | Enterprise Project |
   +=====================+===========================================================+=================================+=============+====================+
   | Creating a Secret   | POST /apis/cci/v2/namespaces/{namespace}/secrets          | CCI:namespaceSubResource:Create | Y           | Y                  |
   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Querying a secret   | GET /apis/cci/v2/namespaces/{namespace}/secrets/{name}    | CCI:namespaceSubResource:Get    | Y           | Y                  |
   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Listing all secrets | GET /apis/cci/v2/namespaces/{namespace}/secrets/{name}    | CCI:namespaceSubResource:List   | Y           | Y                  |
   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Replacing a Secret  | PUT /apis/cci/v2/namespaces/{namespace}/secrets/{name}    | CCI:namespaceSubResource:Update | Y           | Y                  |
   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Updating a Secret   | PATCH /apis/cci/v2/namespaces/{namespace}/secrets/{name}  | CCI:namespaceSubResource:Update | Y           | Y                  |
   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
   | Deleting a Secret   | DELETE /apis/cci/v2/namespaces/{namespace}/secrets/{name} | CCI:namespaceSubResource:Delete | Y           | Y                  |
   +---------------------+-----------------------------------------------------------+---------------------------------+-------------+--------------------+
