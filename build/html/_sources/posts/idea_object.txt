.. _idea_object:



``Idea``
========

.. list-table::
  :widths: 20 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the Post object

  * - ``appId``
    - Id of application to which the idea belongs to

  * - ``commentCount``
    - Count of comments for the idea

  * - ``content``
    - Text content of the idea as html string

  * - ``createdOn``
    - Date when idea was created

  * - ``updatedOn``
    - Date when idea was updated

  * - ``decision``
    - Decision state object:

      | ``comment`` - text comment for decision,
      | ``decidedOn`` - date when decision was made,
      | ``decider`` - post decider info,
      | ``status`` - decision status, can take the next values: ``'open'``, ``'approved'``, ``'amended'``, ``'denied'``
      |
      | `Note: if decision was not made for idea then ``status`` property will be available only`.


  * - ``flags``
    - Array of flags for the problem. Objects have the next schema:

      | ``_id`` - flag Id
      | ``appId`` - application Id
      | ``entityId`` - Id of post that was flagged
      | ``userId`` - Id of user that flagged the post


  * - ``subscribers``
    - Array of subscribers. ``_id`` - user id

  * - ``title``
    - Idea title

  * - ``type``
    - Post type (``'idea'``)

  * - ``user``
    - User that created the idea

  * - ``voteCount``
    - Count of votes for the idea

  * - ``voteValue``
    - Summary votes value for the idea

  * - ``votes``
    - Array of votes. Objects have the next schema:

      | ``_id`` - Id of voted user
      | ``value`` - vote value



Idea post example
-----------------

  .. code-block:: javascript

    {
      "_id" : "538c8fb718e5f54314233b19",
      "appId" : "5359faae8243bf3d6b3079ae",
      "commentCount" : 1,
      "content" : "<p>See this new Pioneer NEX from YouTube</p><p>https://www.youtube.com/watch?v=BXbRCBOtzZQ </p>",
      "createdOn" : "2014-06-02T14:52:38.179Z",
      "updatedOn" : "2014-06-02T14:52:39.179Z",
      "decision": {
            "comment": "<p>This is the best</p>",
            "decidedOn": "2014-09-12T12:04:51.766Z",
            "decider": {
                "_id": "5412bc61b581c78e215a1393",
                "fullName": "Manager name",
                "picture": "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/ivd7o1fdcrfg2h1dkjqw"
            },
            "status": "approved"
      },
      "flags": [
                 {
                    "_id": "5412d593c18cc3a129e4b839",
                    "appId": "5359faae8243bf3d6b3079ae",
                    "entityId": "538c8fb718e5f54314233b19",
                    "userId": "5412bc61b581c78e215a1393"
                 }
      ],
      "subscribers" : [
          {
              "_id" : "535a79378243bf3d6b3079d7"
          }
      ],
      "title" : "Can we integrate our PathFinder mobile app in Android phone for use with the new in-car Entertainment system?",
      "type" : "idea",
      "user" : {
          "_id" : "535a79378243bf3d6b3079d7",
          "fullName" : "johnny.tang",
          "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/ivd7o1fdcrfg2h1dkjqw"
      },
      "voteCount" : 1,
      "voteValue" : 1,
      "votes" : [
          {
              "_id" : "535a79378243bf3d6b3079d7",
              "value" : 1
          }
      ]
    }