.. _problem_object:

``Problem``
===========


.. list-table::
  :widths: 20 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the Post object

  * - ``appId``
    - Id of application to which the problem belongs to

  * - ``commentCount``
    - Count of comments for the problem

  * - ``content``
    - Text content of the problem as html string

  * - ``createdOn``
    - Date when problem was created

  * - ``updatedOn``
    - Date when problem was updated

  * - ``decision``
    - Decision state object:

      | ``comment`` - text comment for decision,
      | ``decidedOn`` - date when decision was made,
      | ``decider`` - post decider info,
      | ``status`` - decision status, can take the next values: ``'open'``, ``'approved'``, ``'amended'``, ``'denied'``
      |
      | `Note: if decision was not made for corresponding solution then ``status`` property will be available only`.


  * - ``flags``
    - Array of flags for the problem. Objects have the next schema:

      | ``_id`` - flag Id
      | ``appId`` - application Id
      | ``entityId`` - Id of post that was flagged
      | ``userId`` - Id of user that flagged the post


  * - ``solutionCount``
    - Count of solutions for the problem

  * - ``subscribers``
    - Array of subscribers. ``_id`` - user id

  * - ``problem``
    - A problem that solution was created for

      | ``_id`` - problem Id
      | ``title`` - problem title
      | ``content`` - problem text content
      | ``open`` - problem state
      | ``createdOn`` - Date when problem was created
      | ``updatedOn`` - Date when problem was updated
      | ``user`` - user that created the problem

  * - ``title``
    - Problem title

  * - ``type``
    - Post type (``'problem'``)

  * - ``user``
    - User that created the problem

  * - ``voteCount``
    - Count of votes for the problem

  * - ``voteValue``
    - Summary votes value for the problem

  * - ``votes``
    - Array of votes. Objects have the next schema:

      | ``_id`` - Id of voted user
      | ``value`` - vote value





Problem post example
--------------------

.. code-block:: javascript

  {
    "_id" : "5355c8bcb117090e18b14013",
    "appId" : "5354bf975ca75754723fe8b6",
    "commentCount" : 1,
    "content" : "<p>Test problem</p>",
    "createdOn" : "2014-04-22T01:41:14.500Z",
    "updatedOn" : "2014-04-22T01:41:16.500Z",
    "decision" : {
        "status" : "open"
    },
    "flags": [
               {
                  "_id": "5412d593c18cc3a129e4b839",
                  "appId": "5359faae8243bf3d6b3079ae",
                  "entityId": "5355c8bcb117090e18b14013",
                  "userId": "5412bc61b581c78e215a1393"
               }
    ],
    "solutionCount" : 1,
    "subscribers" : [
        {
            "_id" : "535582b35ca75754723fe8f6"
        }
    ],
    "title" : "After I posted a comment to an existing problem, I couldn't quite tell if it posted it or not until I scrolled down.",
    "type" : "problem",
    "user" : {
        "_id" : "535582b35ca75754723fe8f6",
        "fullName" : "Ben Gillenwater",
        "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/xouak1iuk935tzzsdl8c"
    },
    "voteCount" : 1,
    "voteValue" : 1,
    "votes" : [
        {
            "_id" : "535582b35ca75754723fe8f6",
            "value" : 1
        }
    ]
  }
