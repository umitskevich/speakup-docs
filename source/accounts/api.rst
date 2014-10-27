
Retrieve current account
========================

Definition:

``GET https://getspeakup.com/api/v1/accounts/current``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/accounts/current \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

Returns :ref:`account object <account_object>`.


Change password
========================

Definition:

``POST https://getspeakup.com/api/v1/accounts/:id/changePassword``

Body parameters:


.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``newPassword``
    - New account password

  * - ``verifyPassword``
    - Verified new account password

  * - ``existingPassword``
    - Existing account password


Example request:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/changePassword \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        newPassword="qwerty" \
        verifyPassword="qwerty" \
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

``POST https://getspeakup.com/api/v1/accounts/:id/forgotPassword``

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

``PUT https://getspeakup.com/api/v1/accounts/changeActiveApp``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``appId``
    - Id of application that user would like to login

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
    "redirect": "https://yourcompany.getspeakup.com"
  }

Connect to Facebook
===================

Definition:

``PUT https://getspeakup.com/api/v1/accounts/:id/facebook/connect``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``id``
    - Id return from oauth workflow

  * - ``accessToken``
    - AccessToken returned from oauth workflow

  * - ``username``
    - username returned from oauth workflow

  * - ``email``
    - Email returned from oauth workflow

Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/facebook/connect \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765
          email="alex@gmail.com" \
          accessToken="074ead10-b21f-40bc-9ec6-4d7as8d280b5" \
          username="alex.p" \
          id="10152187504109372"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200


Disconnect Facebook
===================

Definition:

``PUT https://getspeakup.com/api/v1/accounts/:id/facebook/remove``


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/facebook/remove \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content


Connect to LinkedIn
===================

Definition:

``PUT https://getspeakup.com/api/v1/accounts/:id/linkedin/connect``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``id``
    - Id return from oauth workflow

  * - ``accessToken``
    - AccessToken returned from oauth workflow

  * - ``tokenSecret``
    - TokenSecret returned from oauth workflow

  * - ``email``
    - Email returned from oauth workflow

Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/linkedin/connect \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765
          email="email@gmail.com" \
          tokenSecret="3b1da35-1be6-1151-b5e3-4c7060572a20a" \
          accessToken="074ead10-b21f-40bc-9ec6-4d7as8d280b5" \
          id="2JZG_cHXtz"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200


Disconnect LinkedIn
===================

Definition:

``PUT https://getspeakup.com/api/v1/accounts/:id/linkedin/remove``


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/accounts/535565a95ca75754723fe8e3/linkedin/remove \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content


