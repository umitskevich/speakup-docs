.. _user_object:

``User`` object
===================

Each user belong to particular Application.
User can have different bio, title, roles etc in different applications he belong to.


.. list-table::
  :widths: 20 50
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - Id of the User object

  * - ``appId``
    - Id of application which user belongs to

  * - ``accountId``
    - Id of :ref:`user account <account_object>`.

  * - ``picture``
    - Url to the user picture

  * - ``fullName``
    - User full name

  * - ``email``
    - User email address

  * - ``bio``
    - User info

  * - ``userName``
    - Internal user name, used for mentions

  * - ``groups``
    - Associative array of groups where user participates

  * - ``settings``
    - User notification settings and boolean values for onboarding

  * - ``statistic``
    - User statistic inside his company

  * - ``title``
    - User title

  * - ``roles``
    - Array of user :ref:`roles <user_roles>`.

  * - ``createdOn``
    - Date when user was created (signed up)

Example of user object
----------------------

.. code-block:: javascript

  {
      "_id" : "53aaa7181f0d592c49b7833c",
      "appId" : "53aaa7181f0d592c49b7833a",
      "accountId" : "53aaa7181f0d592c49b7833b",
      "picture" : "https://getspeakup.com/assets/images/profile-image.png",
      "fullName" : "Andrew Orsich",
      "email" : "andrew@paralect.com",
      "bio" : "Some info",
      "userName" : "andrew.orsich",
      "groups": {
              "5416bca3743a8d452ba42014": {
                  "_id": "5416bca3743a8d452ba42014",
                  "isManager": false,
                  "name": "Group A",
                  "statistic": {
                      "comments": 2,
                      "ideas": 4,
                      "problems": 1,
                      "solutions": 0
                  }
              },
              "541843caf50be1146f6e67ef": {
                  "_id": "541843caf50be1146f6e67ef",
                  "isManager": false,
                  "name": "Group B",
                  "statistic": {
                      "comments": 0,
                      "ideas": 1,
                      "problems": 0,
                      "solutions": 0
                  }
              }
      },
      "settings" : {
              "notifications" : {
                  "oncePerDaySendAt" : 16, // time for sending email with 'oncePerDay' frequency in 24h format (16 by default)
                  "emailFrequency" : "instantly"
              },
              "notifyOn" : {
                  "ownPostNewVote" : true,
                  "newComment" : true,
                  "newSolution" : true,
                  "newIdea" : true,
                  "newProblem" : true
              },
              "showOnboarding" : false,
              "postAnonymously" : false,
              "signedUpAsManager" : false,
              "signedUpOnTheirOwn" : true, // if user has signed up on his own using the sign up form this value is equal to 'true', if user has been invited it is equal to 'false'.
              "gettingStarted" : {
                  "inviteManager" : false,
                  "commentPost" : false,
                  "votePost" : false,
                  "createPost" : false,
                  "inviteCoworker" : false,
                  "completeProfile" : false
              },
              "soundsEnabled" : true
      },
      "statistic": {
              "comments": 2,
              "ideas": 1,
              "problems": 0,
              "solutions": 1
      },
      "title" : ".NET / NodeJS developer",
      "roles" : [
          "admin",
          "manager"
      ],
      "createdOn" : "2014-06-25T10:40:24.817Z"
  }


.. _user_roles:

User roles
----------

 1. ``admin`` - can send invitations, update billing information
 2. ``manager`` - can make decisions and see dashboard
