:original_name: connectCciV2PostNamespacedPodExec.html

.. _connectCciV2PostNamespacedPodExec:

Connecting POST Requests to exec of Pod
=======================================

Function
--------

Connect POST requests to exec of Pod.

Calling Method
--------------

For details, see :ref:`Calling APIs <cci_02_0009>`.

URI
---

POST /apis/cci/v2/namespaces/{namespace}/pods/{name}/exec

.. table:: **Table 1** Path Parameters

   +-----------+-----------+--------+-------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                 |
   +===========+===========+========+=============================================================+
   | name      | Yes       | String | Name of the Pod.ExecOptions                                 |
   +-----------+-----------+--------+-------------------------------------------------------------+
   | namespace | Yes       | String | Object name and auth scope, such as for teams and projects. |
   +-----------+-----------+--------+-------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   ========= ========= ======= ===========
   Parameter Mandatory Type    Description
   ========= ========= ======= ===========
   command   No        String    
   container No        String    
   stderr    No        Boolean   
   stdin     No        Boolean   
   stdout    No        Boolean   
   tty       No        Boolean   
   ========= ========= ======= ===========

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                |
   +=================+=================+=================+============================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | User token.                                                                                                                                |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | It can be obtained through the IAM API used to obtain a user token. The value of X-Subject-Token in the response header is the user token. |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | Content-Type    | Yes             | String          | The type of the message body, with a default value of "application/JSON".                                                                  |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   ========= ====== ===========
   Parameter Type   Description
   ========= ====== ===========
   ``-``     String   
   ========= ====== ===========

Example Requests
----------------

None

Example Responses
-----------------

None

Status Codes
------------

=========== ====================
Status Code Description
=========== ====================
200         OK
400         BadRequest
401         Unauthorized
403         Forbidden
404         NotFound
405         MethodNotAllowed
406         NotAcceptable
409         AlreadyExists
415         UnsupportedMediaType
422         Invalid
429         TooManyRequests
500         InternalError
503         ServiceUnavailable
504         ServerTimeout
=========== ====================
