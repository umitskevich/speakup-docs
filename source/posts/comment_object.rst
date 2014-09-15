.. _comment_object:



``Comment``
============


.. list-table::
  :widths: 20 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the Post object

  * - ``appId``
    - Id of application to which the comment belongs to

  * - ``content``
    - Text content of the comment as html string

  * - ``createdOn``
    - Date when comment was created

  * - ``updatedOn``
    - Date when comment was updated

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

  * - ``problem / idea``
    - A problem or idea that comment was created for

      | ``_id`` - idea Id
      | ``title`` - idea title
      | ``content`` - idea text content as html string
      | ``open`` - idea state
      | ``createdOn`` - Date when idea was created
      | ``updatedOn`` - Date when idea was updated
      | ``user`` - user that created the idea


  * - ``type``
    - Post type (``'comment'``)

  * - ``user``
    - User that created the comment

  * - ``voteCount``
    - Count of votes for the comment

  * - ``voteValue``
    - Summary votes value for the comment

  * - ``votes``
    - Array of votes. Objects have the next schema:

      | ``_id`` - Id of voted user
      | ``value`` - vote value


Comment post example
--------------------

.. code-block:: javascript

  {
      "_id" : "535574c15ca75754723fe8ee",
      "appId" : "5354bf975ca75754723fe8b6",
      "content" : "<p>Keith and I discussed this. I am for it, Keith is against it.</p>",
      "createdOn" : "2014-09-12T11:21:27.805Z",
      "updatedOn" : "2014-09-12T11:21:29.805Z",
      "inlineComments": [
              {
                  "_id": "5412d773c18cc3a129e4b83b",
                  "content": "Test inline comment text",
                  "createdOn": "2014-09-12T11:22:27.805Z",
                  "updatedOn": "2014-09-12T11:22:35.807Z",
                  "user": {
                      "_id": "5412bc61b581c78e215a1393",
                      "fullName": "Somebody",
                      "picture": "https://staging.getspeakup.com/images/profile-image.png"
                  }
              }
      ],
      "flags": [
                 {
                    "_id": "5412d593c18cc3a129e4b839",
                    "appId": "5359faae8243bf3d6b3079ae",
                    "entityId": "535574c15ca75754723fe8ee",
                    "userId": "5412bc61b581c78e215a1393"
                 }
      ],
      "subscribers" : [
                {
                    "_id" : "5354bf975ca75754723fe8b7"
                }
      ],
      "idea" : {
                "_id" : "535570b95ca75754723fe8ea",
                "title" : "Emails frequency adjustment",
                "content" : "<p>Besides on/off switch, it's be great to have a config whether emails are sent out immediately, a digest once a day, or a weekly digest</p>",
                "createdOn" : "2014-09-12T11:20:27.805Z",
                "updatedOn" : "2014-09-12T11:20:35.807Z",
                "user" : {
                    "_id" : "5354d1785ca75754723fe8ca",
                    "fullName" : "tomislav.capan",
                    "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/ivd7o1fdcrfg2h1dkjqw"
                }
      },
      "type" : "comment",
      "user" : {
          "_id" : "5354bf975ca75754723fe8b7",
          "fullName" : "Ray Gillenwater",
          "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/f9yyq9ji9b1o9tu9pep6"
      },
      "voteCount" : 1,
      "voteValue" : 1,
      "votes" : [
          {
              "_id" : "5354bf975ca75754723fe8b7",
              "value" : 1
          }
      ]
  }
