:original_name: cci_02_0081.html

.. _cci_02_0081:

Introduction
============

This topic describes fine-grained permissions management for your CCI. If your account does not need individual IAM users, you may skip this topic.

You need to add a user to one or more groups, and assign permissions policies to these groups. The user then inherits permissions from the groups it is a member of. This process is called authorization. After authorization, the user can perform specified operations on CCI based on the permissions.

You can grant users their permissions by using roles and policies. Roles are a type of service-based, coarse-grained authorization mechanism that defines permissions related to user responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   If you want to allow or deny the access to an API, fine-grained authorization is a good choice.

If you use IAM users in your account to call an API, the IAM users must be granted the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user queries pods using an API, the user must have been granted permissions that allow the **CCI:namespaceSubResource:Get** action.

Supported Actions
-----------------

CCI provides system-defined policies that can be directly used in IAM. You can also create custom policies and use them to supplement system-defined policies, implementing more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permission: A statement in a policy that allows or denies certain operations.
-  APIs: REST APIs that can be called in a custom policy.
-  Actions: Added to a custom policy to control permissions for specific operations.
-  IAM or enterprise projects: Type of projects for which an action will take effect. Policies that contain actions supporting both IAM and enterprise projects can be assigned to user groups and take effect in both IAM and Enterprise Management. Policies that only contain actions supporting IAM projects can be assigned to user groups and only take effect for IAM. Such policies will not take effect if they are assigned to user groups in Enterprise Management.

.. note::

   The check mark (Y) and cross symbol (x) indicate that an action takes effect or does not take effect for the corresponding type of projects.

CCI supports the following actions that can be defined in custom policies:

-  :ref:`Namespace management actions <cci_02_0083__table6129054123319>`: actions supported by all namespace management APIs, such as the APIs for creating, querying, updating, and deleting a namespace
-  :ref:`Pod management actions <cci_02_0083__table529334703410>`: actions supported by all pod management APIs, such as the APIs for creating, querying, modifying, and a deleting pod
-  :ref:`Network management actions <cci_02_0083__table19741529184014>`: actions supported by all network management APIs, such as the APIs creating, querying, modifying, and deleting a network
-  :ref:`ConfigMap management actions <cci_02_0083__table833064864119>`: actions supported by all ConfigMap management APIs, such as the APIs for creating, querying, modifying, and deleting a ConfigMap
-  :ref:`Secret management actions <cci_02_0083__table16668191964212>`: actions supported by all secret management APIs, such as the APIs for creating, querying, modifying, and deleting a secret
