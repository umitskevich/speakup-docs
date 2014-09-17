
Retrieve current application
============================

Definition:

``GET https://getspeakup.com/api/v1/applications/:id``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/applications/53aaa7181f0d592c49b7833a \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

Returns :ref:`Application object <application_object>`.



Update application
===================

Definition:

``PUT https://getspeakup.com/api/v1/applications/:id``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``name``
    -  Application name

  * - ``canPostAnonymously``
    -  Boolean value for anonymous posting inside the company


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/applications/53aaa7181f0d592c49b7833a \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        name="New demo name" \
        canPostAnonymously:=false


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK


Unsuccessful response:

If new name was invalid you should see response with errors:

.. code-block:: bash

  HTTP/1.1 400 Bad Request

.. code-block:: javascript

  {
      "errors": [
          {
              "msg": "The company name is required and should be 2 - 30 characters",
              "param": "name"
          }
      ]
  }



Update roles
=============

Definition:

``PUT https://getspeakup.com/api/v1/applications/:id/updateRoles``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``users``
    - Array of updated users *



Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/applications/53aaa7181f0d592c49b7833a/updateRoles \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        users:='[ { "userId": "54195527471842c214145ef8", "roles": ["admin"] }, { "userId": "5419554a471842c214145efd", "roles": [] } ]'


`*` - objects have the next schema:

.. code-block:: javascript

   {
      userId: { type: String },
      roles: [ { type: String } ],
   }

Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK
