Get invitation by Id
=======================

Definition:

``GET https://getspeakup.com/api/v1/:appId/invites/:id``


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

Returns :ref:`Invite object <invite_object>`.



Get invitation list
===================

Definition:

``GET https://getspeakup.com/api/v1/:appId/invites``


Query string parameters:

.. list-table::
  :widths: 10 30 10
  :header-rows: 1

  * - Name
    - Description
    - Default

  * - ``page``
    - Page from invitation list
    - 1

  * - ``limit``
    - Amount of records per page to return
    - 15


Example request:

.. code-block:: bash

  http GET https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites limit==15 page==1 \
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

``POST https://getspeakup.com/api/v1/:appId/invites/sendInvites``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``invites``
    - Email list of invited persons

  * - ``message``
    - Custom message


Example request:

.. code-block:: bash

  http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/sendInvites \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
       invites:='["john@yourcompany.com", "sandra@yourcompany.com", "tom@notyourcompany.com", "invalid_email.com"]' \
       message="Welcome to speak up!"

Example response:

If all above steps were done correctly you should see response that will represent state of invitations:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

   {
       "errors": [
           {
               "code": 400,
               "msg": "Looks like there were a few errors. Please review the following emails: 'invalid_email.com'",
               "param": "email"
           },
           {
               "code": 403,
               "msg": "Whoops! You can only invite 'yourcompany.com' email addresses",
               "param": "email"
           },
           {
               "code": 400,
               "msg": "Invitation has already sent to user(s): john@yourcompany.com",
               "param": "email"
           }
       ],
       "exists": [
           "john@yourcompany.com",
       ],
       "forbidden": [
           "tom@notyourcompany.com"
       ],
       "invalid": [
           "invalid_email.com"
       ],
       "sent": [
           "sandra@yourcompany.com"
       ]
   }


Notes:
        | 1. If application is not subscribed (has no manager) then invitation can be sent to person from the same company only (with the same email domain).
        | 2. If application is subscribed (has manager) and inviter is employee this invitation will require confirmation from manager.




Send manager invitation
=======================

Definition:

``POST https://getspeakup.com/api/v1/:appId/invites/sendManagerInvite``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``email``
    - Manager email

  * - ``message``
    - Custom message


Example request:

.. code-block:: bash

  http POST https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/sendManagerInvite \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
       email="manager@yourcompany.com" \
       message="Welcome to speak up! We would like you be our manager!"

Example response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 200 OK

.. code-block:: javascript

  {
    "_id": "54180e281d36bed1624093a2"
  }


Update an invitation
===================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/invites/:id``

Body parameters:

.. list-table::
  :widths: 20 20
  :header-rows: 1

  * - Name
    - Description

  * - ``isNeedApproval``
    - Boolean value for manager confirmation


Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35 \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765 \
       isNeedApproval:=false


Example response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

    HTTP/1.1 200 OK



Resend an invitation
===================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/invites/:id/resend``


Example request:

.. code-block:: bash

  http PUT https://getspeakup.com/api/v1/53aaa7181f0d592c49b7833a/invites/53d66c7e15aca6cc1f457f35/resend \
       Authorization:Bearer\ 530d7d04f10fa0d7a701762fa1a11078ad15dbd03dd21e1e87b9399fd4f9ce3d0296bd33443dd058a1b871cacac0e765


Example response:

If all above steps were done correctly you should see response like this:

.. code-block:: bash

   HTTP/1.1 204 No Content





Remove an invitation
====================

Definition:

``PUT https://getspeakup.com/api/v1/:appId/invites/:id/delete``


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




