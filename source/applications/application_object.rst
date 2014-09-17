.. _application_object:

``Application`` object
==========================

.. list-table::

  * - Field
    - Description

  * - ``_id``
    - The id of the Application object

  * - ``appUrl``
    - A `vanity url <http://en.wikipedia.org/wiki/Vanity_domain>`_ of application

  * - ``createdOn``
    - Date when application was created

  * - ``email``
    - E-mail of application owner

  * - ``emailDomain``
    - Application domain

  * - ``name``
    - Name of current application (company)

  * - ``ownerAccountId``
    - Id of application owner account

  * - ``selectedPlan``
    - Selected plan for application

  * - ``settings``
    - Application settings

  * - ``status``
    - Application status (can take the next values: ``"noManager"``, ``"subscribed"``, ``"cancelled"``)

  * - ``subDomain``
    - Application subdomain

  * - ``usersCount``
    - The number of active users of application



.. _example_application_object:

Example of an application object
--------------------------------

.. code-block:: javascript

  {
      "_id": "53c7f8b2c924fa53a7a9f4ce",
      "appUrl": "http://yourcompany.getspeakup.com",
      "createdOn": "2014-07-17T16:24:18.907Z",
      "email": "demo@yourcompany.com",
      "emailDomain": "yourcompany.com",
      "name": "Your company name",
      "ownerAccountId": "53c7f8b2c924fa53a7a9f4cf",
      "selectedPlan": "6_user_month",
      "settings": {
          "canPostAnonymously": true
      },
      "status": "subscribed",
      "subDomain": "yourcompany",
      "usersCount": 21
  }




