===================================
Endpoints
===================================

Test Endpoint is: ``https://staging.getspeakup.com/api/v1/``

Most of the api calls must include ``appId`` parameter after the api version.

Each SpeakUp account belong to one or more applications.
``appId`` is an id of the current user application.

Every third party client (mobile app for example) should store current active application id on their side.
The list of user applications can be obtained from user account.

Most of unsuccessful responses are represented as array of errors:

.. code-block:: javascript

   {
     "errors": [
        {
          "param": "email",
          "msg": "Email is not company email.",
          "code": 400
        }
     ]
   }

