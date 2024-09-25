:original_name: cci_03_0005.html

.. _cci_03_0005:

Basic Concepts
==============

CCI provides enhanced features, such as security isolation, fast workload deployment, elastic load balancing, and auto scaling.

The graphical CCI console provides end-to-end user experience. In addition, CCI supports native APIs and kubectl. Before using CCI, you are advised to understand related basic concepts.

Image
-----

A container image is a special file system that provides the programs, libraries, resources, and configuration files required for running a container. It also contains configuration parameters, for example, anonymous volumes, environment variables, and users. An image does not contain any dynamic data, and its content will not be changed after creation.

Container
---------

The relationship between an image and a container is similar to that between a class and an instance in object-oriented programming. Images are static, and containers are entities of running images. A container can be created, started, stopped, deleted, and suspended.

Namespace
---------

A namespace provides a method of allocating resources among multiple users. When you have a large number of projects and personnel, you can define namespaces by project attributes, such as production, test, and development.

Pod
---

A pod is the smallest deployable unit of computing that you can create and manage. A pod is a group of one or more containers, with shared storage resources, a unique IP address, and a specification for how to run the containers.


.. figure:: /_static/images/en-us_image_0197841641.png
   :alt: **Figure 1** Pod

   **Figure 1** Pod

Pods can be used in either of the following ways:

-  One pod that runs a single container: This is the most common use case. You can think of a pod as a wrapper around a single container, but pods can be managed directly rather than containers.
-  Pods that run multiple containers that need to work together:

Pods are rarely created directly. Instead, controllers such as Deployments are used to create and manage pods. Controllers create and manage multiple pods, and provide replica management, rolling upgrade, and self-healing capabilities. A controller typically uses a pod template to create corresponding pods.

Label
-----

A label is a key-value pair attached to an object and is used to transfer user-defined attributes.

Labels are often used to select objects that meet conditions from a group of objects. Labels are currently the most important node grouping method.

For example, you may create labels (**tier**\ =frontend, **app**\ =myapp) to mark frontend pods and labels (**tier**\ =backend, **app**\ =myapp) to mark backend pods. You can then use selectors to select pods with specific labels and apply services or Deployments to these pods.


.. figure:: /_static/images/en-us_image_0197831172.png
   :alt: **Figure 2** Pods organized with labels

   **Figure 2** Pods organized with labels

ConfigMap
---------

A ConfigMap is used to store configuration data as key-value pairs or configuration files. ConfigMaps are similar to secrets, but provide a means of working with strings that do not contain sensitive information.

Secret
------

A secret is an object for storing sensitive data such as authentication information, certificates, and private keys. A secret can be loaded to a container as environment variables when the container is started.
