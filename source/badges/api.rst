 
Get badge by id
==============

Return :ref:`badge <badge_object>` by id

Definition:

``GET https://getspeakup.com/api/v1/:appId/badges/:id``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/badges/1 \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

return :ref:`Badge Object <badge_object>`.

Get all badges
==============

Return array of :ref:`badges <badge_object>`

Definition:

``GET https://getspeakup.com/api/v1/:appId/badges``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/badges \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

return full list of :ref:`badges <badge_object>`.


Get all won badges (awards)
==============

Return array of won badges (badge ID and amount of users who won this badge).

Definition:

``GET https://getspeakup.com/api/v1/:appId/badges/awards``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/badges/awards \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765
    
Example response:

.. code-block:: javascript

  [
    { 
      "_id" : 9,
      "count" : 1 
    }
  ]
  
  
Get single badge awards
==============

Return badge ID and amount of users who won this badge.

Definition:

``GET https://getspeakup.com/api/v1/:appId/badges/awards/:id``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/badges/awards/9 \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765
    
Example response:

.. code-block:: javascript
  
  { 
    "_id" : 9, 
    "count" : 1 
  }  
  
  
Get badges awards by user id
==============

Return user won badges (awards).

Definition:

``GET https://getspeakup.com/api/v1/:appId/badges/awards/user/:id``

Example requests:

.. code-block:: bash

   http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/badges/awards/user/53f080684266ac04066db8c0 \
    Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765
    
Example response:

.. code-block:: javascript
  
  [
    {
      "id" : 9,
      "type" : {
        "id" : 3,
        "name" : "Postulator"
      },
      "level" : {
        "id" : 1,
        "name" : "Cooper"
      },
      "description" : "Postulator badge bronze level",
      "requirement" : {
        "post" : 1
      },
      "count" : 1
    }
  ]