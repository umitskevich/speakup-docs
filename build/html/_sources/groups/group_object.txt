.. _group_object:

``Group`` object
======================

.. list-table::

  * - Field
    - Description

  * - ``_id``
    - Id of the Group object

  * - ``appId``
    - Id of application that group belongs to

  * - ``createdOn``
    - Date when group was created

  * - ``updatedOn``
    - Date when group was updated

  * - ``isAllowAnonymous``
    - Boolean value for anonymous posting inside the group

  * - ``managerId``
    - Id of a group manager (user Id)

  * - ``name``
    - Name of the group

  * - ``statistic``
    - Statistic of the group

  * - ``users``
    - Array of group members (user ids)




.. _example_account_object:

Example of a group object
----------------------------

.. code-block:: javascript

  {
      "_id": "5416bca3743a8d452ba42014",
      "appId": "5412bc60b581c78e215a138a",
      "createdOn": "2014-09-15T10:17:07.569Z",
      "updatedOn": "2014-09-15T10:17:07.569Z",
      "isAllowAnonymous": true,
      "managerId": "5412bc61b581c78e215a1393",
      "name": "Group A",
      "statistic": {
          "usersCount": 2
      },
      "users": [
          "5412bc61b581c78e215a1393",
          "5412bc81b581c78e215a1398"
      ]
  }
