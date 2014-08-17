.. _badge_object:

The ``Badge`` object
===================

Badges types:

1. Connector (1, 10, 100, 1000 invites)
2. Decision Maker (1, 5, 50, 150 approved posts)
3. Innovator (1, 5, 50, 150 approved posts by manager)
4. Opinionator (10, 100, 1000, 10000 votes/comments)
5. Postulator (1, 10, 100, 1000 posts)
6. Thought Leader (10, 100, 1000, 10000 votes on your posts)

Badge levels:

1. Cooper (bronze)
2. Aluminium (silver)
3. Magnesium (gold)
4. Carbon Fiber (?)

Opinionator badge example
---------------------

  .. code-block:: javascript

    {
      id : 5,
      type : { id : this.id, name : this.name },
      level : BaseBadgeService.levels.cooper.id,
      description : 'Opinionator badge bronze level',
      requirement : {
        vote : 10,
        comment : 10
      }
    }