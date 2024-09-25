:original_name: cci_01_0053.html

.. _cci_01_0053:

Creating a Container Group
==========================

Scenario
--------

You can use CCI to quickly create pods for running workloads. On the CCI console, you can view details about all pods, such as basic information, container list, storage volumes, and events. In addition, you can use remote terminals to access pods. You can also delete pods.

Prerequisites
-------------

-  A namespace has been created. If there are no namespaces, create one by referring to :ref:`Creating a Namespace <cci_01_0001__section940418587214>`.
-  The image has been uploaded. For details, see `Uploading an Image Through a Client <https://docs.otc.t-systems.com/software-repository-container/umn/image_management/uploading_an_image_through_the_client.html>`__.

Constraints
-----------

Custom domain name images of the SWR enterprise edition cannot be used to create workloads.

Creating a Pod
--------------

#. Log in to the CCI console.
#. In the navigation pane on the left, choose **Container Groups**. On the displayed page, click **Create Container Group**.
#. On the **Create Container Group** page, specify the basic information.

   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                         | Description                                                                                                                                                              |
   +===================================+==========================================================================================================================================================================+
   | Container Group Name              | -  Enter a name for the container group. The name must be unique in the same account.                                                                                    |
   |                                   | -  Enter 1 to 253 characters. Start and end with a lowercase letter or digit. Use only lowercase letters, digits, hyphens (-), and periods (.).                          |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Namespace                         | Namespace that the container group belongs to.                                                                                                                           |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | (Optional) Description            | Enter a description, which cannot exceed 250 characters.                                                                                                                 |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | CPU Architecture                  | x86                                                                                                                                                                      |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Pod Type                          | General-computing                                                                                                                                                        |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vCPUs                             | Select a value from 0.25 to 64.                                                                                                                                          |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Memory                            | Select the memory based on the selected vCPUs.                                                                                                                           |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | (Optional) Data Storage           | Select a storage volume type and enter a storage volume name.                                                                                                            |
   |                                   |                                                                                                                                                                          |
   |                                   | -  **emptyDir volume**: By default, CCI provides 20 GiB of free storage space, which is shared by emptyDir volumes and the system disk.                                  |
   |                                   | -  **ConfigMaps**: Select a ConfigMap. If no ConfigMaps are available, create one first. For details, see :ref:`Creating a ConfigMap <cci_01_0034__section18512531861>`. |
   |                                   | -  **Secrets**: Select a secret. If no secrets are available, create one first. For details, see :ref:`Creating a Secret <cci_01_0035__section18512531861>`.             |
   |                                   |                                                                                                                                                                          |
   |                                   |    .. note::                                                                                                                                                             |
   |                                   |                                                                                                                                                                          |
   |                                   |       Only emptyDir volumes, ConfigMaps, and secrets are supported. Add a volume to the container group and then mount the volume to the specified container.            |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

4. Configure container settings.

   a. Add basic container information. The total resources of a container cannot exceed the pod flavors.

      .. table:: **Table 1** Basic container information

         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                       |
         +===================================+===================================================================================================================================+
         | Container Name                    | -  The container name must be globally unique.                                                                                    |
         |                                   | -  Enter 1 to 63 characters. Start and end with a lowercase letter or digit. Use only lowercase letters, digits, and hyphens (-). |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
         | Image                             | Select a container image.                                                                                                         |
         |                                   |                                                                                                                                   |
         |                                   | .. caution::                                                                                                                      |
         |                                   |                                                                                                                                   |
         |                                   |    CAUTION:                                                                                                                       |
         |                                   |    Custom domain name images of the SWR enterprise edition cannot be used to create workloads.                                    |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
         | Image Version                     | Select a container image version.                                                                                                 |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
         | vCPUs                             | Specify the vCPUs. The value cannot exceed that in the pod flavors.                                                               |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
         | Memory                            | Specify the memory. The value cannot exceed that in the pod flavors.                                                              |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+

   b. (Optional) Specify advanced container settings.

      .. table:: **Table 2** Advanced container settings

         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                                                                                                  |
         +===================================+==============================================================================================================================================================================================================================================================================================================================================================================================================+
         | Lifecycle                         | Based on Kubernetes, CCI provides containers with `lifecycle hooks <https://kubernetes.io/docs/concepts/containers/container-lifecycle-hooks/>`__, which enable containers to run code triggered by events during their management lifecycle. For example, if you want a container to perform a certain operation before it is stopped, you can register a hook. CCI provides the following lifecycle hooks: |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                                                              |
         |                                   | -  Startup command: Docker ENTRYPOINT commands are used.                                                                                                                                                                                                                                                                                                                                                     |
         |                                   | -  postStart event: This hook is triggered after the application is started.                                                                                                                                                                                                                                                                                                                                 |
         |                                   | -  preStop event: This hook is triggered before the application is stopped.                                                                                                                                                                                                                                                                                                                                  |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Health Check                      | Container health can be checked regularly when the container is running.                                                                                                                                                                                                                                                                                                                                     |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                                                              |
         |                                   | CCI supports the following types of probes:                                                                                                                                                                                                                                                                                                                                                                  |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                                                              |
         |                                   | -  Liveness probe: checks whether a container responds normally and whether a restart is required.                                                                                                                                                                                                                                                                                                           |
         |                                   | -  Ready probe: checks whether a container is ready to respond to requests.                                                                                                                                                                                                                                                                                                                                  |
         |                                   | -  Startup probe: checks whether an application has already started.                                                                                                                                                                                                                                                                                                                                         |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Environment Variables             | Environment variables affect the way a running container will behave. You can update them after deploying the workload.                                                                                                                                                                                                                                                                                      |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Data Storage                      | Volumes can be mounted to containers to read data from files or store data files persistently. To mount a volume to a container, add the volume to the pod first.                                                                                                                                                                                                                                            |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Security Settings                 | Specify a user ID for all the containers to run with. For example, enter **0** to run as user **root**.                                                                                                                                                                                                                                                                                                      |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

5. (Optional) Select an image repository access credential.
