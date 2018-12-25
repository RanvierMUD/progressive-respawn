## progressive-respawn

Ranvier behavior for having a constant respawn happening every [interval]
seconds. As opposed to one giant full area respawn every 10 minutes this will
constantly try to respawn an entity (item/npc) in an area's rooms based on the
entity's respawn chance until it hits the entity's `maxLoad` for the room.

### Configuration

Area-wide respawn interval is set in the `manifest.yml`:

```yaml
title: "Limbo"
behaviors:
  progressive-respawn:
    # seconds between respawn
    interval: 20
```

Configuring an item or NPC to respawn is done inside a room's definition, i.e., the area's `rooms.yml` file:

```yaml
- id: white
  title: "White Room"
  description: "A featureless white room."
  npcs:
    - id: "limbo:trainingdummy"
      # % chance to respawn every interval
      respawnChance: 25
      # Maximum number of this NPC that can exist in the room at once
      maxLoad: 3
  items:
    - id: "limbo:woodenchest"
      respawnChance: 20
      # when this chest respawns completely replace it so its contents get refreshed
      replaceOnRespawn: true
```
