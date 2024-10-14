:original_name: cci_02_0009.html

.. _cci_02_0009:

Calling APIs
============

Public cloud APIs comply with the RESTful API design principles. REST-based web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Unified Resource Locator (URL). A URL is usually in the following format: *https://Endpoint/uri*. **uri** indicates the resource path, that is, the API access path.

Public cloud APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted by using JSON messages, with media type represented by **Application/json**.

For details about how to use APIs, see `API Usage Guidelines <https://docs.otc.t-systems.com/en-us/api/apiug/apig-en-api-180328001.html?tag=API%20Documents>`__.

-  :ref:`Authentication <cci_02_0003>`

.. toctree::
   :maxdepth: 1
   :hidden: 

   authentication
