Get post by id
==============

Returns :ref:`post <post_object>` by its id

Definition:

``GET https://getspeakup.com/api/v1/:appId/posts/:id``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416d3a8abcc72ad356950d6 \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:  Returns :ref:`Post Object <post_object>`.




List posts
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
    - ``'popular'``

  * - ``types``
    - Comma separated list of the :ref:`post types <post_object>`.
    - return all types of posts

  * - ``decision``
    - | Filter posts by decision, valid values are: ``all``, ``open``, ``approved``, ``amended``, ``denied``.
      | In this case `types` - parameter is ignored since decision is specified.
    - ``'all'``

  * - ``parentId``
    - Filter posts by parent post id. If parentId is specified then valid `types` are ``solution`` and ``comment`` only,
      because ``problem`` and ``idea`` do not have parents.
    - none

  * - ``userId``
    - Filter by user who created a post.
    - none

  * - ``groupId``
    - Filter by post group.
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


   <* below api call is identical, just with default query parameters (httpie style) /*>

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts sort=='popular' types=='solution,idea,problem,comment' page==1 limit==15 \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

.. code-block:: javascript

  {
    "pagesCount": 2,
    "results": [PostObject], // * see PostObject definition below
    "totalCount": 23
  }

* :ref:`PostObject <post_object>`.


Notes:

.. list-table::
  :widths: 10 30
  :header-rows: 1

  * - Decision
    - Note

  * - ``all``
    - | If user is a manager then ``'all'`` feed will contain problems, ideas and solutions that require a decision  (solution which parent problem status is open).
      | If user is an ordinary employee then ``'all'`` feed will contain ideas and problems only.

  * - ``open``
    - | If user is a manager then ``'open'`` feed will contain posts that require a decision from him only.
      | If user is an ordinary employee then ``'open'`` feed will contain posts from all his groups and company that require a decision.

  * - ``approved``
    - | ``'approved'`` feed will contain all approved solutions and ideas.

  * - ``amended``
    - | ``'amended'`` feed will contain all amended solutions and ideas.

  * - ``denied``
    - | ``'denied'`` feed will contain all denied solutions and ideas.




Get posts stats
===============

Return count of open, approved, amended, denied posts

Definition:

``GET https://getspeakup.com/api/v1/:appId/posts/stats``

Query string parameters:

.. list-table::
  :widths: 10 30 20
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


   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/stats groupId=='5416bca3743a8d452ba42014' \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

.. code-block:: javascript

 {
    "postMetrics": {
        "all": 6,
        "amended": 0,
        "approved": 4,
        "denied": 0,
        "open": 2
    }
 }

Notes:  Statistic will be counted accordingly to specified decision described in `List posts` notes above.




Create a post
==============

Creates :ref:`post <post_object>`

Definition:

``POST https://getspeakup.com/api/v1/:appId/posts``

Body parameters:

.. list-table::
  :widths: 10 20
  :header-rows: 1

  * - Name
    - Description

  * - ``title``
    - Post title as string

  * - ``content``
    - Post content as html string

  * - ``parentId``
    - Post parentId (for solutions and comments only)

  * - ``type``
    - Post type (``'problem'``, ``'solution'``, ``'idea'``, ``'comment'``)

  * - ``parentType``
    - Post type (``'problem'`` for solution or comment, ``'idea'`` for comment)

  * - ``groupId``
    - Post group id. For company post groupId is null.

  * - ``isAnon``
    - Boolean value for anonymous posting.


Example requests:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        title="Test post title using Api" \
        content="<p>Test post content using Api</p>" \
        parentId=null \
        type="idea" \
        parentType=null \
        groupId="5416bca3743a8d452ba42014" \
        isAnon==false


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
        "_id": "5416d1b1abcc72ad356950d5",
        "groupId": "5416bca3743a8d452ba42014"
    }




Edit a post
==============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/posts/:id``


Body parameters:

.. list-table::
  :widths: 10 30
  :header-rows: 1

  * - Name
    - Description

  * - ``title``
    - Post title as string

  * - ``content``
    - Post content as html string


Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416d3a8abcc72ad356950d6 \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        title="New post title using Api" \
        content="<p>New post content using Api</p>"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
        "_id": "5416d3a8abcc72ad356950d6",
    }





Is post owner
==============

Definition:

``GET https://getspeakup.com/api/v1/:appId/posts/:id/isowner``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416d3a8abcc72ad356950d6/isowner \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:


If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
      "isOwner": true
   }



Decide
=======

Definition:

``PUT https://getspeakup.com/api/v1/:appId/posts/:id/decide``


Body parameters:

.. list-table::
  :widths: 10 30
  :header-rows: 1

  * - Name
    - Description

  * - ``action``
    - Decision for post (``'approved'``, ``'amended'``, ``'denied'``)

  * - ``comment``
    - Comment for decision as html string

  * - ``solutionId``
    - Id of deciding solution (for solutions only)

Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416f6d5b5e794e43c23e761/decide \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        action="amended" \
        comment="<p>Decision test comment</p>" \
        solutionId="5416f6d5b5e794e43c23e761"


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
      "_id": "5416f6d5b5e794e43c23e761"
    }




Share a post
==============

Definition:

``POST https://getspeakup.com/api/v1/:appId/posts/:id/share``


Body parameters:

.. list-table::
  :widths: 10 40
  :header-rows: 1

  * - Name
    - Description

  * - ``emails``
    - Array of emails for sharing

  * - ``message``
    - Custom message text for sharing


Example requests:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416f6d5b5e794e43c23e761/share \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        emails:='["somebody@somecompany.com", "somebodyelse@somecompany.com"]' \
        message="Look at this post"



Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK




Flag a post
==============

Definition:

``POST https://getspeakup.com/api/v1/:appId/posts/:id/flag``


Body parameters:

`There are no body parameters in this request`


Example requests:

.. code-block:: bash

   http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416f6d5b5e794e43c23e761/flag \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765



Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

    {
      "isDeleted": false
    }





Remove a post
==============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/posts/:id/delete``


Example requests:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/posts/5416d3a8abcc72ad356950d6/delete \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

Note:  Parent post removes with all its children



