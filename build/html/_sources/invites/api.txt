Get by Id
===================

Definition:

.. code-block:: bash

   GET https://getspeakup.com/api/v1/:appId/invites/:id


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

:ref:`Invite object <invite_object>`.



Get invitation list
===================

Definition:

.. code-block:: bash

   GET https://getspeakup.com/api/v1/:appId/invites

Query string parameters:
   1. limit - Amount of invitations per page (10 by default)
   2. page - Page from invitation list according to limit


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites limit==10 page==1 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "pagesCount": 1,
       "results": [InviteObject] *, // see definition below
       "totalCount": 3
   }


`*` - Array of :ref:`Invite objects <invite_object>`.


Send invitations
====================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/:appId/invites/sendInvites \
        invites:=[first_email@yourcompany.com, second_email@yourcompany.com]

Body parameters:
   1. invites - Email list of invitee persons

``Note: If user don't have 'Admin' role then invitation can be sent to person from the same company only (with the same email domain).``


Example request:

.. code-block:: bash

  http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/sendInvites \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
       invites:='["john@yourcompany.com", "sandra@yourcompany.com", "tom@notyourcompany.com"]'

Example response:

If all above steps were done correctly you should see response that will represent state of invitations:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "exists": [
           "john@yourcompany.com"
       ],
       "invalid": [
           "tom@notyourcompany.com"
       ],
       "sent": [
           "sandra@yourcompany.com"
       ]
   }





Resend invitation
===================

Definition:

.. code-block:: bash

   PUT https://getspeakup.com/api/v1/:appId/invites/:id/resend



Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35/resend \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content





Delete invitation
===================

Definition:

.. code-block:: bash

   PUT https://getspeakup.com/api/v1/:appId/invites/:id/delete



Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35/delete \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content


If invitation with such Id does not exist response will be like this:

.. code-block:: bash

   HTTP/1.1 404 Not Found




