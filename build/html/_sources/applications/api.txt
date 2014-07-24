
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




Get application statistic
=========================

Definition:

``GET https://getspeakup.com/api/v1/:appId/application/statistic``

Example request:

.. code-block:: bash

  http GET http://localhost:8080/api/v1/53c7f8b2c924fa53a7a9f4ce/application/statistic \
     Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response

.. code-block:: javascript

  {
      "companyName": "Your company",
      "usersCount": 21
  }



Get plans
=========================

Definition:

``GET https://getspeakup.com/api/v1/:appId/application/plans``

Example request:

.. code-block:: bash

  http GET http://localhost:8080/api/v1/53c7f8b2c924fa53a7a9f4ce/application/plans \
     Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response

.. code-block:: javascript

  [
      {
          "amount": 6,
          "maxUsersCount": null,
          "planId": "6_user_month",
          "type": "metered"
      }
  ]
