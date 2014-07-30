Get by Id
====================

Definition:

.. code-block:: bash

   GET https://getspeakup.com/api/v1/:appId/invites/:id


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

:ref:`Invite object <invite_object>`.


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



Delete invitations
====================

Definition:

.. code-block:: bash

   POST https://getspeakup.com/api/v1/:appId/invites/deleteInvites \
        ids:=[first_id, second_id]

Body parameters:
   1. ids - Id list of invitations for deleting


Example request:

.. code-block:: bash

  http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/deleteInvites \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
       ids:='["53d661fefdbd65721f48906a", "53d661fefdbd65721f48906c"]'

Example response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content


