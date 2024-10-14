:original_name: devg_na.html

.. _devg_na:

Namespace and Network
=====================

A namespace provides a method of allocating resources among multiple users. It applies to scenarios where multiple teams or projects exist.

A network is a Kubernetes resource object extended for CCI. You can associate a network with a Virtual Private Cloud (VPC) and subnet so that CCI can use network resources of the public cloud.

Relationship Between a Namespace and Network
--------------------------------------------

A namespace corresponds to a subnet in a VPC, as shown in :ref:`Figure 1 <devg_na__en-us_topic_0127684722_fig714315366295>`. When a namespace is created, it will be associated with a VPC, and a subnet will be created under the VPC. In this namespace, resources such as pods and Services are created in the corresponding VPC and subnet, and the IP addresses in the subnet are used.

If you want to run resources of multiple services in the same VPC, you need to plan subnet CIDR blocks and IP addresses.

.. _devg_na__en-us_topic_0127684722_fig714315366295:

.. figure:: /_static/images/en-us_image_0000001909077313.png
   :alt: **Figure 1** Relationship between namespaces and VPC subnets

   **Figure 1** Relationship between namespaces and VPC subnets

Scenarios Where Multiple Namespaces Are Used
--------------------------------------------

Because namespaces enable partial environment isolation, you can create different namespaces, such as production, test, and development namespaces based on project attributes when there are a large number of projects and persons.
