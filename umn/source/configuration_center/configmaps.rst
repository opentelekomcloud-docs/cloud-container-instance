:original_name: cci_01_0034.html

.. _cci_01_0034:

ConfigMaps
==========

ConfigMaps are objects that you can use to store the configurations required by applications. After you create a ConfigMap, you can use it as a file in a containerized application.

.. _cci_01_0034__section18512531861:

Creating a ConfigMap
--------------------

#. Log in to the CCI console. In the navigation pane on the left, choose **Configuration Center**.
#. Select a namespace and click the **ConfigMaps** tab.
#. Click **Create from YAML** in the upper left corner and edit the YAML file. For details about the YAML file, see :ref:`YAML format <cci_01_0034__li5976173124010>`.

   .. note::

      CCI supports both JSON and YAML, and the file size cannot exceed 1 MB.

#. Click **OK**.

Using a ConfigMap
-----------------

After a ConfigMap is created, you can mount it to a container as a storage volume during pod creation. For example, mount a ConfigMap named **system-preset-aeskey** to a container and set the storage volume name to **volume1**.

ConfigMap File Format
---------------------

A ConfigMap resource file must be in either JSON or YAML format, and the file size cannot exceed 1 MB.

-  JSON format

   Example file: **configmap.json**

   .. code-block::

      {
        "kind": "ConfigMap",
        "apiVersion": "v1",
        "metadata": {
          "name": "nginxconf",
          "namespace": "cci-namespace-demo"
        },
        "data": {
          "nginx.conf": "server {\n    listen       80;\n    server_name  localhost;\n\n    location / {\n        root   html;\n        index  index.html index.htm;\n    }\n}"
        }
      }

-  .. _cci_01_0034__li5976173124010:

   YAML format

   Example file: **configmap.yaml**

   .. code-block::

      kind: ConfigMap
      apiVersion: v1
      metadata:
        name: nginxconf
        namespace: cci-namespace-demo
      data:
        nginx.conf: |-
          server {
              listen       80;
              server_name  localhost;

              location / {
                  root   html;
                  index  index.html index.htm;
              }
          }
