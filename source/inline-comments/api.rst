
Get an inline-comment by id
========================

Definition:

``GET https://getspeakup.com/api/v1/:appId/inline-comments/:id``

`:id` - inline-comment id

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/inline-comments/541718573d06dee047090edf \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
        "_id": "541718573d06dee047090edf",
        "content": "Test inline-comment text",
        "createdOn": "2014-09-15T16:48:23.215Z",
        "type": "inlineComment",
        "updatedOn": "2014-09-15T16:48:23.216Z",
        "user": {
            "_id": "5412bc61b581c78e215a1393",
            "fullName": "John Doe",
            "picture": "http://localhost:8080/assets/images/2-frontend/profile-image.png"
        }
    }



Create an inline-comment
========================

Definition:

``POST https://getspeakup.com/api/v1/:appId/inline-comments``

Body parameters:

.. list-table::
  :widths: 10 20
  :header-rows: 1

  * - Name
    - Description

  * - ``content``
    - Inline-comment content

  * - ``parentId``
    - Id of parent post (solution or comment)

  * - ``isAnon``
    -  Boolean value for anonymous posting.



Example requests:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/inline-comments \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        content="Test inline-comment text" \
        parentId="541725813d06dee047090ee1" \
        isAnon:=false



Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
        "_id": "541726053d06dee047090ee3"
    }



Edit an inline-comment
======================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/inline-comments/:id``

Body parameters:

.. list-table::
  :widths: 10 20
  :header-rows: 1

  * - Name
    - Description

  * - ``content``
    - Post title as string


Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/inline-comments/541726053d06dee047090ee3 \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        content="New inline-comment content"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
        "_id": "541726053d06dee047090ee3",
    }



Remove an inline-comment
========================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/inline-comments/:id/delete``

Body parameters:

`There are no body parameters in this request`


Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/inline-comments/541726053d06dee047090ee3/delete \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765



Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK




