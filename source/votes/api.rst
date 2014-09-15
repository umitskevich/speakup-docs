Make a vote
============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/votes/:operation``

`:operation` - voting operation (``'up'``, ``'down'``, ``'un'``)

Body parameters:

.. list-table::
  :widths: 10 40
  :header-rows: 1

  * - Name
    - Description

  * - ``postId``
    -  Post id


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/votes/up \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        postId="5416d1b1abcc72ad356950d5"

Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

    HTTP/1.1 200 OK

