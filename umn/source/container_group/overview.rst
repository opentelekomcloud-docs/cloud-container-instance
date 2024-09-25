:original_name: en-us_topic_0000001955196756.html

.. _en-us_topic_0000001955196756:

Overview
========

What Is a Pod or Container Group?
---------------------------------

Pods (or container groups) are the smallest deployable units of computing that you can create and manage. A pod or a container group is a group of one or more containers, with shared storage, a unique IP address, and a specification for how to run the containers.

Pods can be used in either of the following ways:

-  A pod runs a single container. This is the most common use case. You can consider a pod as a wrapper around a single container. Pods can be managed directly rather than containers.

-  A pod runs multiple containers that need to work together. In this scenario, a pod can encapsulate an application that is running in a main container and several sidecar containers. As shown in :ref:`Figure 1 <en-us_topic_0000001955196756__en-us_topic_0116111750_fig347141918551>`, the main container serves as a web server that provides file services from a fixed directory, and the sidecar container periodically downloads files to the directory.

   .. _en-us_topic_0000001955196756__en-us_topic_0116111750_fig347141918551:

   .. figure:: /_static/images/en-us_image_0000001991238669.png
      :alt: **Figure 1** Pod

      **Figure 1** Pod
