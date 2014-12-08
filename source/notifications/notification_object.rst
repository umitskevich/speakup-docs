.. _notification_object:

``Notification`` object
==========================

.. list-table::

  * - Field
    - Description

  * - ``_id``
    - The id of Notification object

  * - ``appId``
    - Id of application that notification belongs to

  * - ``userId``
    - User Id that notification was created for

  * - ``entityId``
    - Id of an entity which related to notification (usually it is the :ref:`post object <post_object>`)

  * - ``type``
    - Notification type ( ``'new-problem'``, ``'new-idea'``, ``'new-solution'``, ``'new-problem-comment'``, ``'new-idea-comment'``,
      ``'new-solution-inlineComment'``, ``'new-problem-comment-inlineComment'``, ``'new-idea-comment-inlineComment'``, ``'new-vote'``,
      ``'new-decision'``, ``'new-mention'``, ``'admin-rights-granted'``, ``'admin-rights-revoked'`` )

  * - ``data``
    - Metadata that contains information about entity which related to notification

  * - ``createdOn``
    - Date when notification entity was created

  * - ``state``
    - Notification reading state (``"read"``, ``"unread"``)


.. _example_invite_object:

Example of notification object
--------------------------------

.. code-block:: javascript

  {
      "_id" : "54820c475246175f95533b52",
      "appId" : "54820be95246175f95533b1c",
      "userId" : "54820c095246175f95533b44",
      "entityId" : "54820c475246175f95533b51",
      "type" : "new-problem",
      "data" : {
          "post" : {
              "shareUrl" : "https://getspeakup.com/post/problem/54820c475246175f95533b51/details/solutions?share=true",
              "viewUrl" : "https://getspeakup.com/post/problem/54820c475246175f95533b51/details/solutions",
              "user" : {
                  "title" : "",
                  "picture" : "https://secure.gravatar.com/avatar/e1602610fef7a9e0ac19bf5a8af99c52?s=128&r=PG&d=identicon",
                  "fullName" : "cat",
                  "_id" : "54820bea5246175f95533b3a"
              },
              "updatedOn" : ISODate("2014-12-05T19:49:27.762Z"),
              "decision" : {
                  "status" : "open"
              },
              "voteValue" : 0,
              "groupName" : "Cat",
              "content" : "<p><span class=\"rangySelectionBoundary\">&#65279;</span>2</p>",
              "title" : "2",
              "type" : "problem",
              "_id" : "54820c475246175f95533b51"
          }
      },
      "createdOn" : ISODate("2014-12-05T19:49:27.794Z"),
      "state" : "unread",
  }





