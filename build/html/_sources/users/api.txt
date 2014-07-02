
Retrieve current user
=====================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/current``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/current \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`User object <account_object>`.


Retrieve user by id
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/:id``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`User object <account_object>`.