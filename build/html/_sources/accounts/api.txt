
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


Change password
========================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/accounts/:id/createPassword \
        newPassword=new_password \
        existingPassword=old_password

Example request:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/changePassword \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        newPassword="qwerty" \
        existingPassword="123456"

Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content

If there were errors in password validation response will be like this:

.. code-block:: bash

   HTTP/1.1 400 Bad Request


.. code-block:: javascript

  {
     "errors": [
         {
             "field": "existingPassword",
             "message": "Invalid current password"
         }
     ]
  }



Forgot password
========================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/accounts/:id/forgotPassword

Example request:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/forgotPassword \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK




Change active application
=========================

Definition:

.. code-block:: bash

   PUT https://getspeakup.com/api/v1/accounts/changeActiveApp \
        appId=appId_to_login

Body parameters:
   1. appId - Id of application that user would like to login

Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/accounts/changeActiveApp \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        appId="53d2c3515c15b4a7bda023fe"

Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

  {
    "redirect": "https://getspeakup.com"
  }

