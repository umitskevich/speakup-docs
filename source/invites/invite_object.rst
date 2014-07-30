.. _invite_object:

The ``Invite`` object
==========================

.. list-table::

  * - Field
    - Description

  * - ``_id``
    - The id of the Invite object

  * - ``appId``
    - Id of application that invitation belongs to

  * - ``createdOn``
    - Date when invite entity was created

  * - ``email``
    - Email of person that was invited to application

  * - ``inviterId``
    - Id of user that sent invitation

  * - ``token``
    - Token for invite entity


.. _example_invite_object:

Example of an invite object
--------------------------------

.. code-block:: javascript

  {
      "_id": "53d66c7e15aca6cc1f457f35",
      "appId": "53aaa7181f0d592c49b7833a",
      "createdOn": "2014-07-28T14:47:16.641Z",
      "email": "sandra@yourcompany.com",
      "inviterId": "53d2646ac8f9d5169fb03206",
      "token": "228fb7ada78c6b390d54d67142099487714419e6a478a32eee7efe36210f5f5a79cd30002ca061c65c4508120363da9e"
  }





