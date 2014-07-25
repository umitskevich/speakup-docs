
Retrieve current user
=====================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/current``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/current \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`User object <user_object>`.


Retrieve user by id
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/:id``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`User object <user_object>`.



Update decision maker
=====================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/:appId/users/updateDecisionMaker \
        id=demo_decision_maker_id

Body parameters:
   1. id - Id of user that will be updated as Decision Maker


Example request:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/updateDecisionMaker \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        id="53d2ba3dd9f854b7bb77cc98"


Successful response:

If all above steps were done correctly you should get response as   `HTTP/1.1 204 No Content`

