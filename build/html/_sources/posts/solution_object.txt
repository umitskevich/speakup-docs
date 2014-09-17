.. _solution_object:

``Solution``
============


.. list-table::
  :widths: 20 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the Post object

  * - ``appId``
    - Id of application to which the solution belongs to

  * - ``commentCount``
    - Count of comments for the solution

  * - ``content``
    - Text content of the solution as html string

  * - ``createdOn``
    - Date when solution was created

  * - ``updatedOn``
    - Date when solution was updated

  * - ``decision``
    - Decision state object:

      | ``comment`` - text comment for decision,
      | ``decidedOn`` - date when decision was made,
      | ``decider`` - post decider info,
      | ``status`` - decision status, can take the next values: ``'open'``, ``'approved'``, ``'amended'``, ``'denied'``
      |
      | `Note: if decision was not made then ``status`` property will be available only`.


  * - ``inlineComments``
    - Array of inline comments. `Inline comment can be posted for Solutions and Comments only.` Objects have the next schema:

      | ``_id`` - inline comment Id
      | ``content`` - inline comment text content
      | ``createdOn`` - date when inline comment was created
      | ``updatedOn`` - date when inline comment was updated
      | ``user`` - user that created inline comment


  * - ``flags``
    - Array of flags for the solution. Objects have the next schema:

      | ``_id`` - flag Id
      | ``appId`` - application Id
      | ``entityId`` - Id of post that was flagged
      | ``userId`` - Id of user that flagged the post

  * - ``subscribers``
    - Array of subscribers. ``_id`` - user id

  * - ``problem``
    - A problem that solution was created for

      | ``_id`` - problem Id
      | ``title`` - problem title
      | ``content`` - problem text content as html string
      | ``open`` - problem state
      | ``createdOn`` - Date when problem was created
      | ``updatedOn`` - Date when problem was updated
      | ``user`` - user that created the problem

  * - ``title``
    - Solution title

  * - ``type``
    - Post type (``'solution'``)

  * - ``user``
    - User that created the solution

  * - ``voteCount``
    - Count of votes for the solution

  * - ``voteValue``
    - Summary votes value for the solution

  * - ``votes``
    - Array of votes. Objects have the next schema:

      | ``_id`` - Id of voted user
      | ``value`` - vote value



Solution post example
---------------------

  .. code-block:: javascript

   {
      "_id" : "536bbe290635cc730c130f87",
      "appId" : "5359faae8243bf3d6b3079ae",
      "commentCount" : 0,
      "content" : "<p>This issue is on Ray's \"short-term features list\" and it would probably come \"it in the next couple of weeks.\"</p>",
      "createdOn" : "2014-09-12T11:21:27.805Z",
      "updatedOn" : "2014-09-12T11:21:29.805Z",
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
      "inlineComments": [
                    {
                        "_id": "5412d773c18cc3a129e4b83b",
                        "content": "Test inline comment text",
                        "createdOn": "2014-09-12T11:22:27.805Z",
                        "updatedOn": "2014-09-12T11:22:35.807Z",
                        "user": {
                            "_id": "5412bc61b581c78e215a1393",
                            "fullName": "Somebody",
                            "picture": "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/ivd7o1fdcrfg2h1dkjqw"
                        }
                    }
      ],
      "flags": [
                  {
                     "_id": "5412d593c18cc3a129e4b839",
                     "appId": "5359faae8243bf3d6b3079ae",
                     "entityId": "536bbe290635cc730c130f87",
                     "userId": "5412bc61b581c78e215a1393"
                  }
      ],
      "subscribers": [
              {
                  "_id": "5412bc61b581c78e215a1393"
              }
      ],
      "problem" : {
          "_id" : "5369e4140635cc730c130f27",
          "title" : "Speakup needs to allow formatting text",
          "content" : "<p>Currently longer posts turn into impenetrable walls of text. It'd be nice to have some method of having paragraphs.</p>",
          "open" : false,
          "createdOn" : "2014-09-12T11:19:27make .805Z",
          "updatedOn" : "2014-09-12T11:19:29.805Z",
          "user" : {
              "_id" : "5369c8670635cc730c130f16",
              "fullName" : "olli-pekka.valtonen",
              "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/qmdqkq0vnq5icg7hgpol"
          }
      },
      "title" : "I have already sent an email to Ray regarding this:",
      "type" : "solution",
      "user" : {
          "_id" : "535a96fb8243bf3d6b3079df",
          "fullName" : "Alfred Lam",
          "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/l3aug7djhre7dtkooa7s"
      },
      "voteCount" : 1,
      "voteValue" : 1,
      "votes" : [
          {
              "_id" : ObjectId("535a96fb8243bf3d6b3079df"),
              "value" : 1
          }
      ]
   }