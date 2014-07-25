.. _account_object:

The ``Account`` object
======================

.. list-table::

  * - Field
    - Description

  * - ``_id``
    - The id of the Account object

  * - ``activeAppId``
    - Active application Id on the web site. Third parties can use it to initially set user active application.

  * - ``apps``
    - Array of applications account belong to. ``_id`` - applicationId, ``name`` - application name.

  * - ``createdOn``
    - Date when account was created (sign up date)

  * - ``email``
    - Email address of the account

  * - ``fullName``
    - full name of the account


.. _example_account_object:

Example of an account object
----------------------------

.. code-block:: javascript

  {
    "_id" : "535565a95ca75754723fe8e3",
    "activeAppId" : ObjectId("5354bf975ca75754723fe8b6"),
    "apps" : [
        {
            "_id" : "5354bf975ca75754723fe8b6",
            "name" : "SpeakUp Test Account"
        },
        {
            "_id" : "5354bf975ca75754723fe8b6",
            "name" : "Personal Account"
        }
    ],
    "createdOn" : "2014-05-17T12:27:33.103Z",
    "email" : "demo@getspeakup.com",
    "fullName" : "Demo Account"
  }