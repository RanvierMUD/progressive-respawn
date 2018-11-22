## progressive-respawn

Ranvier behavior for having a constant respawn happening every [interval]
seconds. As opposed to one giant full area respawn every 10 minutes this will
constantly try to respawn an entity (item/npc) in an area's rooms based on the
entity's respawn chance until it hits the entity's `maxLoad` for the room.

### Configuration

`interval`: _`number`_ `(30)`
:    Number of seconds between respawn tries
