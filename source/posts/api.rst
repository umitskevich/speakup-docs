
List all posts
==============

Definition:

``GET https://getspeakup.com/api/v1/:appId/posts``

Query string parameters:

.. list-table::
  :widths: 10 30 10
  :header-rows: 1

  * - Name
    - Description
    - Default

  * - ``sort``
    - Sort order for the posts list. Can be ``popular`` or ``newest``.
    - ``popular``

  * - ``types``
    - Comma separated list of the :ref:`Post types <post_object>`.
    - return all types of posts

  * - ``decision``
    - Query posts by decision, valid values are: all, open, amended, denied, approved.
    - all

  * - ``parentId``
    - Filter by parent post id, if specified valid ``types`` only ``solution`` and ``comment``,
      because ``problem`` and ``idea`` does not have parents
    - none

  * - ``userId``
    - Filter by user, who created a post
    - none

  * - ``groupId``
    - Filter by post group
    - none

  * - ``page``
    - Page number to return.
    - 1

  * - ``limit``
    - Number of records to return.
    - 15

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

   <* below api call is identical, just with default query parameters /*>
   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts?sort=popular&types=solution,idea,problem,comment&page=1&limit=15 \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

.. code-block:: javascript

  {
    "pagesCount": 2,
    "results": [PostObject], // see PostObject definition below
    "totalCount": 23
  }

:ref:`PostObject <post_object>`.

Get posts stats
===============

Return count of open, approved, amended, denied posts

Definition:

``GET https://getspeakup.com/api/v1/:appId/posts/stats``

Query string parameters:

.. list-table::
:widths: 10 30 10
  :header-rows: 1

  * - Name
    - Description
    - Default

  * - ``groupId``
    - Filter statistic for specified group
    - none

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/stats \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

.. code-block:: javascript

 {
    "postMetrics": {
        "amended": 0,
        "approved": 4,
        "denied": 0,
        "open": 2
    }
 }

Get post by id
==============

Return :ref:`post <post_object>` by id

Definition:

``GET https://getspeakup.com/api/v1/:appId/posts/:id``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/53aaa7191f0d592c49b7833e \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

return :ref:`Post Object <post_object>`.