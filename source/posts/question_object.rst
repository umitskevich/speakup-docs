.. _question_object:

``Question``
===========


.. list-table::
  :widths: 20 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the Post object

  * - ``appId``
    - Id of application to which the question belongs to

  * - ``commentCount``
    - Count of comments for the question

  * - ``content``
    - Text content of the question as html string

  * - ``createdOn``
    - Date when question was created

  * - ``updatedOn``
    - Date when question was updated

  * - ``decision``
    - Decision state object:

      | ``comment`` - text comment for decision,
      | ``decidedOn`` - date when decision was made,
      | ``decider`` - post decider info,
      | ``status`` - decision status, can take the next values: ``'open'``, ``'approved'``
      |
      | `Note: if decision was not made for corresponding answer then ``status`` property will be available only`.


  * - ``flags``
    - Array of flags for the question. Objects have the next schema:

      | ``_id`` - flag Id
      | ``appId`` - application Id
      | ``entityId`` - Id of post that was flagged
      | ``userId`` - Id of user that flagged the post


  * - ``answerCount``
    - Count of answers for the question

  * - ``subscribers``
    - Array of subscribers. ``_id`` - user id

  * - ``title``
    - Question title

  * - ``type``
    - Post type (``'question'``)

  * - ``user``
    - User that created the question

  * - ``voteCount``
    - Count of votes for the question

  * - ``voteValue``
    - Summary votes value for the question

  * - ``votes``
    - Array of votes. Objects have the next schema:

      | ``_id`` - Id of voted user
      | ``value`` - vote value





Question post example
--------------------

.. code-block:: javascript

  {
      "_id" : "548761708f8749bd4aa0a66c",
      "answerCount" : 1,
      "appId" : "548760638f8749bd4aa0a639",
      "commentCount" : 0,
      "content" : "<p>How do I adhere to the dental plan?</p>",
      "createdOn" : ISODate("2014-12-09T20:54:08.324Z"),
      "decision" : {
          "status" : "open"
      },
      "files" : [],
      "flags" : [ 
          {
              "_id" : "548764418f8749bd4aa0a67c",
              "appId" : "548760638f8749bd4aa0a639",
              "entityId" : "548761708f8749bd4aa0a66c",
              "userId" : "548763168f8749bd4aa0a672"
          }
      ],
      "groupId" : null,
      "groupName" : "Bar",
      "inlineComments" : [],
      "isAnon" : false,
      "isSpirit" : false,
      "solutionCount" : 0,
      "subscribers" : [ 
          {
              "_id" : "548760658f8749bd4aa0a664"
          }
      ],
      "tags" : [],
      "title" : "Dental plan",
      "type" : "question",
      "updatedOn" : ISODate("2014-12-09T20:54:08.324Z"),
      "user" : {
          "_id" : "548760658f8749bd4aa0a664",
          "fullName" : "Alex",
          "picture" : "http://www.gravatar.com/avatar/445669b69294f02457778ef0ee7fbfa9?s=128&r=PG&d=identicon",
          "title" : ""
      },
      "voteCount" : 1,
      "voteValue" : 1,
      "votes" : [ 
          {
              "_id" : "548763168f8749bd4aa0a672",
              "value" : 1
          }
      ]
  }
