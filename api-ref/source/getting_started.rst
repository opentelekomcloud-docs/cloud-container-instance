:original_name: cci_02_0011.html

.. _cci_02_0011:

Getting Started
===============

Overview
--------

You can call APIs to create a pod. An Nginx image is used as an example to show how you can create a pod.

The Nginx image is from the open-source image center, and the container uses 1 vCPU and 2 GiB of memory.

For details about how to call APIs, see :ref:`Calling APIs <cci_02_0009>`.

Procedure
---------

#. Call the API described in :ref:`Creating a Namespace <createcciv2namespace>` to create a namespace.
#. Call the API described in :ref:`Creating a Network <createyangtsev2namespacednetwork>` to create a network, and associate the network with a VPC and subnet.
#. Call the API described in :ref:`Creating a Pod <createcciv2namespacedpod>` to create an Nginx pod.

Creating an Nginx Pod
---------------------

#. Call the API described in :ref:`Creating a Namespace <createcciv2namespace>` to create a namespace.

   .. code-block::

      {
        "apiVersion": "cci/v2",
        "kind": "Namespace",
        "metadata": {
          "name": "namespace-test"
        }
      }

   You must specify the following parameters:

   -  **name**: namespace name.

#. Call the API described in :ref:`Creating a Network <createyangtsev2namespacednetwork>` to create a network, and associate the network with a VPC and subnet.

   .. code-block::

      {
        "apiVersion": "yangtse/v2",
        "kind": "Network",
        "metadata": {
          "annotations": {
            "yangtse.io/domain-id": "51ed88507a244b6eb36270c0250fcc96",
            "yangtse.io/project-id": "a81f079abca74e83b47af9a586048b24"
          },
          "name": "test-network",
          "namespace": "namespace-test"
        },
        "spec": {
          "networkType": "underlay_neutron",
          "securityGroups": [
            "470b6a8f-612e-4284-a788-c6900ac32fce"
          ],
          "subnets": [
            {
              "subnetID": "c6dd31e3-d217-4b31-bb60-eb30322c75b8"
            }
          ]
        }
      }

   You must specify the following parameters:

   -  **name**: name of a network object.
   -  **securityGroups**: security group ID, which can be obtained on the **Security Groups** page.
   -  **yangtse.io/domain-id**: account ID, which can be obtained by following the procedure in :ref:`Obtaining an Account ID <cci_02_1002>`.
   -  **yangtse.io/project-id**: project ID, which can be obtained by following the procedure in :ref:`Obtaining a Project ID <cci_02_1001>`.
   -  **subnetID**: ID of the subnet in the VPC, which can be obtained on the VPC console or by calling the API for querying subnets.

#. Call the API described in :ref:`Creating a Pod <createcciv2namespacedpod>` to create an Nginx pod.

   In this example, a pod whose name is **nginx** and specifications are set to 1 vCPU and 2 GiB of memory will be created from the open-source image nginx:stable-alpine-perl. After the API is called, CCI creates a container running nginx.

   .. code-block::

      {
        "apiVersion": "cci/v2",
        "kind": "Pod",
        "metadata": {
          "name": "nginx"
        },
        "spec": {
          "containers": [
            {
              "image": "nginx:stable-alpine-perl",
              "name": "container-0",
              "resources": {
                "limits": {
                  "cpu": "1",
                  "memory": "2Gi"
                },
                "requests": {
                  "cpu": "1",
                  "memory": "2Gi"
                }
              }
            }
          ],
          "imagePullSecrets": [
            {
              "name": "imagepull-secret"
            }
          ]
        }
      }

   You must specify the following parameters:

   -  **name**: pod name
   -  **containers**: container information

      -  **image**: image used to create containers
      -  name: container name
      -  **resources.limits**: resource limits for a container. The resources used by a container cannot exceed the limits.
      -  **resources.requests**: resources requested by a container

   After the pod is created, you can view it on the CCI console.

   |image1|

.. |image1| image:: /_static/images/en-us_image_0000001874007888.png
