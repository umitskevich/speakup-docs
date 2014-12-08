Get user notifications list
===========================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/:id/notifications``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53d66c7e15aca6cc1f457f35/notifications \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765

Example response:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "pagesCount": 1,
       "results": [NotificationObject] *, // see definition below
       "totalCount": 6
   }

`*` - Array of all unread and read (on the last 2 days) :ref:`notification objects <notification_object>`.




Get unread notifications count
==============================

Definition:

``GET https://getspeakup.com/api/v1/:appId/users/:id/notifications/count``

Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53d66c7e15aca6cc1f457f35/notifications/count \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "count": 4
   }



Mark notification as read
==========================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/notifications/:notificationId/markAsRead``

Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53d66c7e15aca6cc1f457f35/notifications/5485aab8850b65321e33b0d6/markAsRead \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

.. code-block:: bash

   HTTP/1.1 200 OK



Mark all notification as read
====================================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/users/:id/notifications/markAllAsRead``

Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/users/53d66c7e15aca6cc1f457f35/notifications/markAllAsRead \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

.. code-block:: bash

   HTTP/1.1 200 OK
