:original_name: readCciV2NamespacedPodLog.html

.. _readCciV2NamespacedPodLog:

Reading Logs of the Specified Pod
=================================

Function
--------

Read logs of the specified Pod.

Calling Method
--------------

For details, see :ref:`Calling APIs <cci_02_0009>`.

URI
---

GET /apis/cci/v2/namespaces/{namespace}/pods/{name}/log

.. table:: **Table 1** Path Parameters

   +-----------+-----------+--------+-------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                 |
   +===========+===========+========+=============================================================+
   | name      | Yes       | String | Name of the Pod.                                            |
   +-----------+-----------+--------+-------------------------------------------------------------+
   | namespace | Yes       | String | Object name and auth scope, such as for teams and projects. |
   +-----------+-----------+--------+-------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +------------------------------+-----------+---------+-----------------------------------------------+
   | Parameter                    | Mandatory | Type    | Description                                   |
   +==============================+===========+=========+===============================================+
   | container                    | No        | String  |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | follow                       | No        | Boolean |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | insecureSkipTLSVerifyBackend | No        | Boolean |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | limitBytes                   | No        | Integer |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | pretty                       | No        | String  | If 'true', then the output is pretty printed. |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | previous                     | No        | Boolean |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | sinceSeconds                 | No        | Integer |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | tailLines                    | No        | Integer |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+
   | timestamps                   | No        | Boolean |                                               |
   +------------------------------+-----------+---------+-----------------------------------------------+

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
409         Conflict
415         UnsupportedMediaType
422         Invalid
429         TooManyRequests
500         InternalError
503         ServiceUnavailable
504         ServerTimeout
=========== ====================
