
Get all plans
=============

Definition:

``GET https://getspeakup.com/api/v1/:appId/billing/plans``

Example request:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/billing/plans \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "applicationPlansOverride": {
           "5354bf975ca75754723fe8b6": "free",
           "5359faae8243bf3d6b3079ae": "free",
           "5377649abc92a0a319096ab1": "free",
           "53a9ae15cea12f8f4418c48b": "free",
           "53b6161edf54f56625c34dad": "free",
           "5400e52ab02dc9d03dd4aa5f": "free",
           "54015eb76637f1753ebbcaf0": "free"
       },
       "basicPlan": {
           "amount": 6,
           "maxUsersCount": null,
           "planId": "6_user_month",
           "type": "metered"
       },
       "freePlan": {
           "amount": 0,
           "maxUsersCount": null,
           "planId": "free",
           "type": "static"
       },
       "plans": [
           {
               "amount": 6,
               "maxUsersCount": null,
               "planId": "6_user_month",
               "type": "metered"
           },
           {
               "amount": 0,
               "maxUsersCount": null,
               "planId": "free",
               "type": "static"
           }
       ]
   }




Change a plan
===============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/billing``


Body parameters:


.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``card``
    -  Token that was generated by Stripe service from card number.

  * - ``selectedPlan``
    -  Selected plan for application.



Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/billing \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        card='tok_14LZVn2VjFqKat8xCdtihCmt' \
        selectedPlan='6_user_month'


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content


If there were errors in validation response will be like this:

.. code-block:: bash

   HTTP/1.1 400 Bad Request

   {
       "errors": [
           {
               "msg": "Please, select a plan",
               "param": "selectedPlan",
           }
       ]
   }





Downgrade application
=====================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/billing/downgrade``


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/billing/downgrade \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content
