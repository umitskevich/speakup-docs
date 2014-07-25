
Retrieve current application
============================

Definition:

``GET https://getspeakup.com/api/v1/:appId/application/current``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53c7f8b2c924fa53a7a9f4ce/application/current \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`Application object <application_object>`.



Update application (company) name
=================================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/:appId/application/updateCompanyName \
        companyName=new_demo_name

Body parameters:
   1. companyName - New name for application


Example request:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53c7f8b2c924fa53a7a9f4ce/application/updateCompanyName \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        companyName="New demo name"



Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: javascript

  {
     "status": "200 OK"
  }


Unsuccessful response:

If error occurs on server side response should be like this

.. code-block:: javascript

  {
     { status: '500 ERROR', error: {} }
  }


