
Retrieve current user
=====================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/current``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/current \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

Returns :ref:`User object <user_object>`.


Get user by id
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/:id``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

Returns :ref:`User object <user_object>`.


Get user list
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users``


Query string parameters:

.. list-table::
  :widths: 10 30 10
  :header-rows: 1

  * - Name
    - Description
    - Default

  * - ``sort``
    - Sorting field for users. It consists of two parts separated by colon, the first part is field name, the second one is order direction.
      Sorting can be performed by multiple fields separated by comma, in this case the first criteria has higher priority.
    - ``'fullName:1'``

  * - ``role``
    - User role for filtering.
    - none

  * - ``text``
    - Value for searching criteria (searching by 'fullName' field).
    - none

  * - ``groupId``
    - Group id for filtering.
    - none

  * - ``page``
    - Page number.
    - 1

  * - ``limit``
    - Number of records to return.
    - 15


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users sort=='rolesCount:-1,fullName:1' limit==15 page==1 groupId=='541843caf50be1146f6e67ef' \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

.. code-block:: javascript

   {
       "pagesCount": 1,
       "results": [UserObject] *, // see definition below
       "totalCount": 6
   }

`*` - Array of :ref:`user objects <user_object>`.



Upgrade to manager
====================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/upgradeToManager``


Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``token``
    -  Generated token from credit card number by stripe service



Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c/upgradeToManager \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        token="tok_14LZVn2VjFqKat8xCdtihCmt"


Successful response:

If all above steps were done correctly you should get response like this:

.. code-block:: bash

   HTTP/1.1 200 OK



Save user settings
====================

Definition:


``PUT https://getspeakup.com/api/v1/:appId/users/:id``


Body parameters:


.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``email``
    -  User email.

  * - ``fullName``
    -  User full name.

  * - ``title``
    -  User job title.

  * - ``bio``
    -  Information about user.

  * - ``settings``
    -  Notification settings. *

  * - ``roles``
    -  Array of roles to assign.

  * - ``picture``
    -  User picture url.

  * - ``picturePublicId``
    -  Picture public Id.



Example request:

.. code-block:: bash


   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
        email="new_email@yourcompany.com" \
        fullName="John Doe" \
        title="Node.js developer" \
        bio="Here is information about user" \
        settings:='{ "notifications": { "emailFrequency": "onceEvery15Minutes" }, "notifyOn": { "newProblem": true, "newIdea": true, "newSolution": true, "newComment": false, "ownPostNewVote": true }, "postAnonymously": true }' \
        picture="http://res.cloudinary.com/7adf6ngw/image/upload/sample.jpg"



`*` - settings is json object with the next schema:

.. code-block:: javascript

     settings: {

         notifications: {
            emailFrequency: { type: String, enum: ['never', 'instantly', 'onceEvery15Minutes', 'oncePerDay'] },
            oncePerDaySendAt: { type: Number } // time for sending email with 'oncePerDay' frequency in 24h format (16 by default)
         },
         notifyOn: {
            newProblem: { type: Boolean },
            newIdea: { type: Boolean },
            newSolution: { type: Boolean },
            newComment: { type: Boolean },
            ownPostNewVote: { type: Boolean }
         },
         showOnboarding: { type: Boolean },
         postAnonymously: { type: Boolean },
         signedUpAsManager: { type: Boolean },
         signedUpOnTheirOwn: {type: Boolean }, // if user has signed up on his own using the sign up form this value is equal to 'true', if user has been invited it is equal to 'false'.
         gettingStarted: {
            completeProfile: { type: Boolean },
            inviteCoworker: { type: Boolean },
            createPost: { type: Boolean },
            votePost: { type: Boolean },
            commentPost: { type: Boolean },
            inviteManager: { type: Boolean }
         },
         soundsEnabled: { type: Boolean }
     }


Successful response:

If all above steps were done correctly you should get response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content



If there were errors in settings validation response will be like this:

.. code-block:: bash

   HTTP/1.1 400 Bad Request


.. code-block:: javascript

    {
      "errors": [
          {
              "param": "email",
              "msg": "Email is not company email."
          }
      ]
    }




Change picture
====================

Definition:

``POST https://getspeakup.com/api/v1/:appId/users/:id/changePicture``


Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``file``
    -  Uploading image.


Example request:

.. code-block:: bash

   http -f POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c/changePicture \
	 Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
	 file@~/images/your_avatar.jpg


Successful response:

If all above steps were done correctly you should get response like this:

.. code-block:: bash

   HTTP/1.1 200 OK


.. code-block:: javascript

  {
      "height": 273,
      "thumbnailUrl": "https://res.cloudinary.com/speakup/image/upload/c_fill,g_face,h_180,w_180/kiezh3uksp6zw1ombzwb",
      "url": "http://res.cloudinary.com/speakup/image/upload/v1406727634/kiezh3uksp6zw1ombzwb.jpg",
      "width": 184
  }



Download facebook picture
=========================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/downloadFacebookPicture``


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c/downloadFacebookPicture \
	 Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765



Successful response:

If all above steps were done correctly you should get response like this:

.. code-block:: bash

   HTTP/1.1 200 OK


.. code-block:: javascript

  {
      "picture": "http://graph.facebook.com/accountFacebookId/picture?type=large"
  }



Remove picture
====================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/removePicture``


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c/removePicture \
         	Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly response should be like this (contains path to default image):

.. code-block:: bash

   HTTP/1.1 200 OK


.. code-block:: javascript

  {
      "picture": "http://yourcompany.getspeakup.com/assets/images/2-frontend/profile-image.svg"
  }




Request manager access
======================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/requestManagerAccess``


Example request:

.. code-block:: bash

   http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c/requestManagerAccess \
         	Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly response should be like this (contains path to default image):

.. code-block:: bash

   HTTP/1.1 200 OK



Remove a user
==============

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/delete``

Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53aaa7181f0d592c49b7833c/delete \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:


If all above steps were done correctly you should get response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content


If user with such Id does not exist response will be like this:

.. code-block:: bash

   HTTP/1.1 404 Not Found