
Get all plans
=============

Definition:

.. code-block:: bash

   GET https://getspeakup.com/api/v1/:appId/billing/plans

Example request:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/billing/plans \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   [
     {
         "amount": 6,
         "maxUsersCount": null,
         "planId": "6_user_month",
         "type": "metered"
     }
   ]
