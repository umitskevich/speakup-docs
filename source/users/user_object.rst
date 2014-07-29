.. _user_object:

The ``User`` object
===================

Each user belong to particular Application.
User can have different bio, title, roles etc in different applications he belong to.


.. list-table::
  :widths: 10 40
  :header-rows: 1

  * - Field
    - Description

  * - ``_id``
    - The id of the User object

  * - ``appId``
    - Id of application to which user belong

  * - ``accountId``
    - Id of :ref:`User Account <account_object>`.

  * - ``picture``
    - Url to the user picture

  * - ``fullName``
    - full name of the user

  * - ``email``
    - Email address of the user

  * - ``bio``
    - Bio of user

  * - ``userName``
    - Internal user name, used for mentions.

  * - ``settings``
    - Notifications settings

  * - ``statistic``
    - User statistic according to his posts

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
      "bio" : "",
      "userName" : "andrew.orsich",
      "settings" : {
          "notifications" : {
              "email" : true
          },
          "notifyOn" : {
              "ownPostNewComment" : true,
              "ownPostNewSolution" : true,
              "newIdea" : true,
              "newProblem" : true
          }
      },
      "statistic": {
              "comments": 2,
              "ideas": 1,
              "problems": 0,
              "solutions": 1
      },
      "title" : "",
      "roles" : [
          "admin",
          "decisionMaker"
      ],
      "createdOn" : "2014-06-25T10:40:24.817Z"
  }


.. _user_roles:

User roles
----------

 1. admin - can send invites, update billing information
 2. decisionMaker - can make decisions and see dashboard
