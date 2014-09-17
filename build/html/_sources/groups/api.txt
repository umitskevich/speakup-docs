Get group by Id
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/groups/:id``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/groups/5416bca3743a8d452ba42014 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

Returns :ref:`Group object <group_object>`.



Get group list
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/groups``

Query string parameters:

.. list-table::
  :widths: 10 30 10
  :header-rows: 1

  * - Name
    - Description
    - Default

  * - ``page``
    - Page from group list
    - 1

  * - ``limit``
    - Amount of records per page to return
    - 15


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/groups limit==15 page==1 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "pagesCount": 1,
       "results": [GroupsObject] *, // see definition below
       "totalCount": 4
   }


`*` - Array of :ref:`group objects <group_object>`.




Create a group
==============

Definition:

``POST https://getspeakup.com/api/v1/:appId/groups``

Body parameters:

.. list-table::
  :widths: 10 30
  :header-rows: 1

  * - Name
    - Description

  * - ``name``
    - Group name

  * - ``isAllowAnonymous``
    - Boolean value for anonymous posting inside the group

  * - ``users``
    - Array of group members (user ids)

  * - ``managerId``
    - Group manager Id (user id)

Example requests:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/groups \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        name="New test group name" \
        isAllowAnonymous:=true \
        users:='["5412bc61b581c78e215a1393", "5412bc81b581c78e215a1398"]' \
        managerId="5412bc81b581c78e215a1398"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

    HTTP/1.1 200 OK




Edit a group
==============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/groups/:id``

Body parameters:

.. list-table::
  :widths: 10 30
  :header-rows: 1

  * - Name
    - Description

  * - ``name``
    - Group name

  * - ``isAllowAnonymous``
    - Boolean value for anonymous posting inside the group

  * - ``users``
    - Array of group members (user ids)

  * - ``managerId``
    - Group manager Id (user id)


Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/groups/5416bca3743a8d452ba42014 \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        name="Updated test group name" \
        isAllowAnonymous:=false \
        users:='["5412bc61b581c78e215a1393", "5412bc81b581c78e215a1398"]' \
        managerId="5412bc61b581c78e215a1393"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

  HTTP/1.1 200 OK



Remove a group
==============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/groups/:id/delete``


Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/groups/5416bca3743a8d452ba42014/delete \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

  HTTP/1.1 200 OK
