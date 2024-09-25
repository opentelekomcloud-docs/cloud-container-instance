:original_name: cci_01_0035.html

.. _cci_01_0035:

Secrets
=======

Secrets are objects that you can use to store sensitive data such as authentication information, certificates, and private keys. You can load a secret to a container as an environment variable when the container is started or mount a secret to a container as a file.

.. note::

   It is recommended that you encrypt the uploaded secrets.

.. _cci_01_0035__section18512531861:

Creating a Secret
-----------------

#. Log in to the CCI console. In the navigation pane on the left, choose **Configuration Center**.

#. Select a namespace and click the **Secrets** tab.

#. Click **Create from YAML** in the upper left corner and edit the YAML file. For details about the YAML file, see :ref:`YAML format <cci_01_0035__li6120118172019>`.

   .. note::

      CCI supports both JSON and YAML, and the file size cannot exceed 2 MB.

#. Click **OK**.

   You can view the newly created secret in the secret list.

Using a Secret
--------------

After a secret is created, you can mount it to a container as a storage volume during pod creation. For example, mount a secret named **aksk-secret** to a container and set the storage volume name to **volume2**.

Secret File Format
------------------

-  .. _cci_01_0035__li6120118172019:

   **secret.yaml** resource description file

   For example, you can use a secret to obtain the following key-value pairs and encrypt them for an application:

   key1: value1

   key2: value2

   The **secret.yaml** file is defined as below. (Base64 encoding is required for the value of each key. For details about the Base64 encoding method, see :ref:`Base64 Encoding <cci_01_0035__section175000605919>`.)

   .. code-block::

      apiVersion: v1
      kind: Secret
      metadata:
        name: mysecret           #Secret name
        annotations:
          description: "test"
        labels:
          label-01: value-01
          label-02: value-02
      data:
        key1: dmFsdWUx    #Base64 encoding required
        key2: dmFsdWUy  #Base64 encoding required
      type: Opaque         #The type must be Opaque.

-  **secret.json** resource description file

   The content is as follows:

   .. code-block::

      {
          "apiVersion": "v1",
          "kind": "Secret",
          "metadata": {
              "annotations": {
                  "description": "test"
              },
              "labels": {
                  "label-01": "value-01",
                  "label-02": "value-02"
              },
              "name": "mysecret"
          },
          "data": {
              "key1": "dmFsdWUx",
              "key2": "dmFsdWUy"
          },
          "type": "Opaque"
      }

.. _cci_01_0035__section175000605919:

Base64 Encoding
---------------

To perform Base64 encoding on a character string, run the **echo -n** *{Content to be encoded}* **\| base64** command.

.. code-block::

   root@ubuntu:~# echo -n "3306" | base64
   MzMwNg==
