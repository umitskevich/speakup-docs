.. _answer_object:

``Answer``
============


.. list-table::
  :widths: 20 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the Post object

  * - ``appId``
    - Id of application to which the answer belongs to

  * - ``commentCount``
    - Count of comments for the answer

  * - ``content``
    - Text content of the answer as html string

  * - ``createdOn``
    - Date when answer was created

  * - ``updatedOn``
    - Date when answer was updated

  * - ``decision``
    - Decision state object:

      | ``comment`` - text comment for decision,
      | ``decidedOn`` - date when decision was made,
      | ``decider`` - post decider info,
      | ``status`` - decision status, can take the next values: ``'open'``, ``'approved'``
      |
      | `Note: if decision was not made then ``status`` property will be available only`.


  * - ``inlineComments``
    - Array of inline comments. `Inline comment can be posted for Solutions, Answers and Comments only.` Objects have the next schema:

      | ``_id`` - inline comment Id
      | ``content`` - inline comment text content
      | ``createdOn`` - date when inline comment was created
      | ``updatedOn`` - date when inline comment was updated
      | ``user`` - user that created inline comment


  * - ``flags``
    - Array of flags for the answer. Objects have the next schema:

      | ``_id`` - flag Id
      | ``appId`` - application Id
      | ``entityId`` - Id of post that was flagged
      | ``userId`` - Id of user that flagged the post

  * - ``subscribers``
    - Array of subscribers. ``_id`` - user id

  * - ``question``
    - A question that answer was created for

      | ``_id`` - question Id
      | ``title`` - question title
      | ``content`` - question text content as html string
      | ``open`` - question state
      | ``createdOn`` - Date when question was created
      | ``updatedOn`` - Date when question was updated
      | ``user`` - user that created the question

  * - ``title``
    - Answer title

  * - ``type``
    - Post type (``'answer'``)

  * - ``user``
    - User that created the answer

  * - ``voteCount``
    - Count of votes for the answer

  * - ``voteValue``
    - Summary votes value for the answer

  * - ``votes``
    - Array of votes. Objects have the next schema:

      | ``_id`` - Id of voted user
      | ``value`` - vote value



Answer post example
---------------------

  .. code-block:: javascript

   {
    "_id" : "548761aa8f8749bd4aa0a66e",
    "answerCount" : 0,
    "appId" : "548760638f8749bd4aa0a639",
    "commentCount" : 0,
    "content" : "<p>Just talk to Mary, she'll be able to get you setup in no time.</p>",
    "createdOn" : ISODate("2014-12-09T20:55:06.290Z"),
    "decision" : {
        "status" : "open"
    },
    "files" : [],
    "flags" : [ 
        {
            "_id" : "548769978f8749bd4aa0a67f",
            "appId" : "548760638f8749bd4aa0a639",
            "entityId" : "548761aa8f8749bd4aa0a66e",
            "userId" : "548763168f8749bd4aa0a672"
        }
    ],
    "groupId" : null,
    "groupName" : "Bar",
    "inlineComments" : [],
    "isAnon" : false,
    "isSpirit" : false,
    "question" : {
        "_id" : "548761708f8749bd4aa0a66c",
        "title" : "Dental plan",
        "content" : "<p>How do I adhere to the dental plan?</p>",
        "open" : true,
        "createdOn" : ISODate("2014-12-09T20:54:08.324Z"),
        "updatedOn" : ISODate("2014-12-09T20:54:08.324Z"),
        "user" : {
            "_id" : "548760658f8749bd4aa0a664",
            "fullName" : "Alex",
            "picture" : "http://www.gravatar.com/avatar/445669b69294f02457778ef0ee7fbfa9?s=128&r=PG&d=identicon",
            "title" : ""
        }
    },
    "solutionCount" : 0,
    "subscribers" : [ 
        {
            "_id" : "548760658f8749bd4aa0a664"
        }
    ],
    "tags" : [],
    "title" : "Ask Mary",
    "type" : "answer",
    "updatedOn" : ISODate("2014-12-09T20:55:06.290Z"),
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