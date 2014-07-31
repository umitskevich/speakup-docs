
Retrieve current application
============================

Definition:

.. code-block:: bash

  GET https://getspeakup.com/api/v1/applications/:id

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/applications/53aaa7181f0d592c49b7833a \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`Application object <application_object>`.



Update application (company) name
=================================

Definition:

.. code-block:: bash

   PUT https://getspeakup.com/api/v1/applications/:id/updateCompanyName \
        companyName=new_name

Body parameters:
   1. companyName - New name for application


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/applications/53aaa7181f0d592c49b7833a/updateCompanyName \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        companyName="New demo name"



Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK


Unsuccessful response:

If new name was invalid you should see response with errors:

.. code-block:: bash

  HTTP/1.1 400 Bad Request

.. code-block:: javascript

  {
      "errors": [
          {
              "msg": "The company name is required and should be 2 - 30 characters",
              "param": "companyName",
              "value": ""
          },
      ]
  }



