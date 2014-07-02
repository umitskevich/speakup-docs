.. _post_object:

The ``Post`` object
===================

The ``Post`` object can be one of the following types:

1. Idea
2. Problem
3. Solution
4. Comment

Solution post example
---------------------

  .. code-block:: javascript

   {
      "_id" : "536bbe290635cc730c130f87",
      "appId" : "5359faae8243bf3d6b3079ae",
      "commentCount" : 0,
      "content" : "This issue is on Ray's \"short-term features list\" and it would probably come \"it in the next couple of weeks.\"",
      "createdOn" : "2014-05-08T17:26:01.962Z",
      "decision" : {
          "status" : "open"
      },
      "inlineComments" : [],
      "problem" : {
          "_id" : "5369e4140635cc730c130f27",
          "title" : "Speakup needs to allow formatting text",
          "content" : "Currently longer posts turn into impenetrable walls of text. It'd be nice to have some method of having paragraphs.",
          "open" : false,
          "createdOn" : "2014-05-07T07:43:16.964Z",
          "updatedOn" : "2014-05-07T07:43:16.964Z",
          "user" : {
              "_id" : "5369c8670635cc730c130f16",
              "fullName" : "olli-pekka.valtonen",
              "picture" : "https://res.cloudinary.com/speakup/image/upload/c_fill,h_180,w_180/qmdqkq0vnq5icg7hgpol"
          }
      },
      "title" : "I have already sent an email to Ray regarding this:",
      "type" : "solution",
      "updatedOn" : "2014-05-08T17:26:01.962Z",
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


Idea post example
-----------------

  .. code-block:: javascript

    {
      "_id" : "538c8fb718e5f54314233b19",
      "appId" : "5359faae8243bf3d6b3079ae",
      "commentCount" : 1,
      "content" : "<p>See this new Pioneer NEX from YouTube</p><p><br/></p><p>https://www.youtube.com/watch?v=BXbRCBOtzZQ </p>",
      "createdOn" : "2014-06-02T14:52:39.179Z",
      "decision" : {
          "status" : "open"
      },
      "inlineComments" : [],
      "subscribers" : [
          {
              "_id" : "535a79378243bf3d6b3079d7"
          }
      ],
      "title" : "Can we integrate our PathFinder mobile app in Android phone for use with the new in-car Entertainment system?",
      "type" : "idea",
      "updatedOn" : "2014-06-02T14:52:39.179Z",
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


Problem post example
--------------------

.. code-block:: javascript

  {
    "_id" : "5355c8bcb117090e18b14013",
    "appId" : "5354bf975ca75754723fe8b6",
    "commentCount" : 1,
    "content" : ".",
    "createdOn" : "2014-04-22T01:41:16.500Z",
    "decision" : {
        "status" : "open"
    },
    "inlineComments" : [],
    "solutionCount" : 1,
    "subscribers" : [
        {
            "_id" : "535582b35ca75754723fe8f6"
        }
    ],
    "title" : "After I posted a comment to an existing problem, I couldn't quite tell if it posted it or not until I scrolled down.",
    "type" : "problem",
    "updatedOn" : "2014-04-22T01:41:16.500Z",
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


Comment post example
--------------------

.. code-block:: javascript

  {

      "_id" : "535574c15ca75754723fe8ee",
      "appId" : "5354bf975ca75754723fe8b6",
      "commentCount" : 0,
      "content" : "Keith and I discussed this. I am for it, Keith is against it.",
      "createdOn" : "2014-04-21T19:42:57.119Z",
      "decision" : {
          "status" : "open"
      },
      "idea" : {
          "_id" : "535570b95ca75754723fe8ea",
          "title" : "Emails frequency adjustment",
          "content" : "Besides on/off switch, it's be great to have a config whether emails are sent out immediately, a digest once a day, or a weekly digest",
          "createdOn" : "2014-04-21T19:25:45.084Z",
          "updatedOn" : "2014-04-21T19:25:45.084Z",
          "user" : {
              "_id" : "5354d1785ca75754723fe8ca",
              "fullName" : "tomislav.capan",
              "picture" : "https://staging.getspeakup.com/images/profile-image.png"
          }
      },
      "inlineComments" : [],
      "solutionCount" : 0,
      "subscribers" : [
          {
              "_id" : "5354bf975ca75754723fe8b7"
          }
      ],
      "type" : "comment",
      "updatedOn" : "2014-04-21T19:42:57.119Z",
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