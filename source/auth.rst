==============
Authentication
==============

Third party app authorization
-----------------------------

To get started you must obtain ``client_id`` and ``client_secret`` from SpeakUp.
In the documentation we will use ``demo_client_id`` as the ``client_id``
and ``demo_client_secret`` as the ``client_secret``.

User authorization
------------------

To make api calls you need to authorise current user. It can be done using following method:

.. code-block:: bash

  http POST https://getspeakup.com/api/oauth/token grant_type=password \
    client_id=demo_client_id \
    client_secret=demo_client_secret \
    username=andrew@paralect.com \
    password=123456


User authorization via facebook social account
----------------------------------------------

Parameters:

.. list-table::
:widths: 10 30
  :header-rows: 1

  * - Name
    - Description

  * - ``username``
    - Must be `facebook`

  * - ``password``
    - Facebook Access Token returned by Oauth workflow

To make api calls you need to authorise current user. It can be done using following method:

.. code-block:: bash

  http POST https://getspeakup.com/api/oauth/token grant_type=password \
    client_id=demo_client_id \
    client_secret=demo_client_secret \
    username=facebook \
    password=074ead10-b21f-40bc-9ec6-4d7ec8d280b5


User authorization via linkedin social account
----------------------------------------------

Parameters:

.. list-table::
:widths: 10 30
  :header-rows: 1

    * - Name
      - Description

    * - ``username``
    - Must be `linkedin`

  * - ``password``
    - Linkedin Access Token returned by Oauth workflow

To make api calls you need to authorise current user. It can be done using following method:

.. code-block:: bash

  http POST https://getspeakup.com/api/oauth/token grant_type=password \
    client_id=demo_client_id \
    client_secret=demo_client_secret \
    username=linkedin \
    password=074ead10-b21f-40bc-9ec6-4d7ec8d280b5



Successful authorization response
---------------------------------
This response is returned for authorization via user login/password as well as social access token.
If all above steps were done correctly you should see response like this:

.. code-block:: javascript

  {
    "access_token": "530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765",
    "expires_in": 3600,
    "refresh_token": "df30f9b747c4c57413396e13ad427a5cc71fc2cc785e1e1fc1434401a2499a28d424cf6af0ffd03fcb6180089fbfad59",
    "token_type": "Bearer"
  }

Invalid username or password response
-------------------------------------

.. code-block:: javascript

  {
    "error": "invalid_grant",
    "error_description": "Invalid resource owner credentials"
  }

Invalid client_id or client_secret response
-------------------------------------------

In that case you will see ``401 (Unauthorized)`` status code in response


Authorization of all subsequent api calls
-----------------------------------------

All subsequent requests should contains ``Authorization`` header with following value: ``'Bearer {{access_token}}``.
Where ``{{access_token}}`` is a value received from /token api call.

For example:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/accounts/current \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765