
Retrieve current account
========================

Definition:

.. code-block:: bash

   GET https://getspeakup.com/api/v1/accounts/current

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/accounts/current \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

:ref:`Account object <account_object>`.


Change active application
=========================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/accounts/changeActiveApp \
        appId="appId_to_login"

Body parameters:
   1. appId - Id of application that user would like to login

Example request:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/accounts/changeActiveApp \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        appId="53d2c3515c15b4a7bda023fe"

Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: javascript

  {
    "redirect": "https://getspeakup.com"
  }

