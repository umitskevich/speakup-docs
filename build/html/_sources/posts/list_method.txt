
List all posts
=================

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
    - Query posts by decision, valid values are: open, amended, denied, approved.
      If specified ``types`` will be ``idea`` and ``solution``.
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
    "results": [PostObject], //see PostObject definition below
    "totalCount": 23
  }

:ref:`PostObject <post_object>`.
