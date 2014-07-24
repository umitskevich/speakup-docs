.. _application_object:

The ``Application`` object
==========================

.. list-table::

  * - Field
    - Description

  * - ``_id``
    - The id of the Application object

  * - ``appUrl``
    - The base SpeakUp url

  * - ``createdOn``
    - Date when application was created

  * - ``email``
    - E-mail of application owner

  * - ``emailDomain``
    - Application domain

  * - ``maxInvitesCount``
    - Maximum number of possible invitations for current application according to selected plan (as string)

  * - ``name``
    - Name of current application (company)

  * - ``ownerAccountId``
    - Id of application owner

  * - ``selectedPlan``
    - Selected plan for application

  * - ``status``
    - Application status (can take the next values: "noManager", "onTrial", "trialEnded", "subscribed", "cancelled")

  * - ``stripe``
    - todo

  * - ``subDomain``
    - Application subdomain

  * - ``trialStartedOn``
    - Date when trial version was started




.. _example_application_object:

Example of an application object
--------------------------------

.. code-block:: javascript

  {
      "__v": 0,
      "_id": "53c7f8b2c924fa53a7a9f4ce",
      "appUrl": "https://getspeakup.com",
      "createdOn": "2014-07-17T16:24:18.907Z",
      "email": "demo@yourcompany.com",
      "emailDomain": "yourcompany.com",
      "maxInvitesCount": "Infinity",
      "name": "Your company",
      "ownerAccountId": "53c7f8b2c924fa53a7a9f4cf",
      "selectedPlan": "trial",
      "status": "onTrial",
      "stripe": {
          "customerId": null,
          "subscriptionId": null
      },
      "subDomain": "yourcompany",
      "trialStartedOn": "2014-07-18T16:01:24.881Z"
  }



