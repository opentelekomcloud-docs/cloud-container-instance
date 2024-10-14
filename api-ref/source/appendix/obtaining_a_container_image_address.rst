:original_name: cci_02_1003.html

.. _cci_02_1003:

Obtaining a Container Image Address
===================================

Cloud Container Instance (CCI) supports both images in the container registry and those uploaded to SoftWare Repository for Container (SWR). Where,

-  SWR has synchronized some common images from the container registry so that you can use the images named in the format of **Image name:Tag** (for example, **nginx:alpine**) on the internal network. You can query the synchronized images on the SWR console.
-  SWR images can be obtained by using **Image Pull Command**. After an image is uploaded, you can obtain its address.
