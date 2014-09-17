Search
==========

Definition:

``GET https://getspeakup.com/api/v1/:appId/search``


Query string parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``term``
    -  Search criteria


Example request:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/search term=='test post' \
        Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Successful response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

    HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "posts": {
           "comment": [],
           "idea": [
               {
                   "__v": 1,
                   "_id": "5416d1b1abcc72ad356950d5",
                   "appId": "5412bc60b581c78e215a138a",
                   "commentCount": 0,
                   "content": "<p>Test post content using Api</p>",
                   "createdOn": "2014-09-15T11:46:57.828Z",
                   "decision": {
                       "comment": "<p>ggrgrt</p>",
                       "decidedOn": "2014-09-15T14:06:04.389Z",
                       "decider": {
                           "_id": "5412bc61b581c78e215a1393",
                           "fullName": "John Doe",
                           "picture": "http://yourcompany.getspeakup/assets/images/2-frontend/profile-image.png"
                       },
                       "status": "approved"
                   },
                   "flags": [],
                   "groupId": "5416bca3743a8d452ba42014",
                   "groupName": "Updated test group name",
                   "inlineComments": [],
                   "isAnon": false,
                   "isSpirit": false,
                   "solutionCount": 0,
                   "subscribers": [
                       {
                           "_id": "5412bc61b581c78e215a1393"
                       }
                   ],
                   "title": "Test post title using Api",
                   "type": "idea",
                   "updatedOn": "2014-09-15T11:46:57.828Z",
                   "user": {
                       "_id": "5412bc61b581c78e215a1393",
                       "fullName": "John Doe",
                       "picture": "http://yourcompany.getspeakup/assets/images/2-frontend/profile-image.png"
                   },
                   "voteCount": 1,
                   "voteValue": 1,
                   "votes": [
                       {
                           "_id": "5412bc61b581c78e215a1393",
                           "value": 1
                       }
                   ]
               }
           ],
           "problem": [],
           "solution": []
       },
       "users": []
   }



