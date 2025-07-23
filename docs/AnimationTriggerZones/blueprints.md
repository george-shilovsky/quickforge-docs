# Blueprint Events & Interfaces

This section explains how to use Blueprint events and the `ATZCharacterInterface` to integrate your character or objects with Animation Trigger Zones.

---

## Built-in Blueprint Events

The `AnimTriggerZone` component exposes several assignable events.

### Available Events

| Event Name                   | Triggered When...                           |
|------------------------------|----------------------------------------------|
| **OnEnter**                  | Actor enters the trigger zone                |
| **OnExit**                   | Actor exits the trigger zone                 |
| **OnAnimationStart**         | Animation montage starts playing             |
| **OnAnimationEnd**           | Animation montage ends or is interrupted     |
| **OnQueueEnter**             | Actor is added to the waiting queue          |
| **OnQueueExit**              | Actor is removed from the queue              |
| **OnInteractionTriggeredEvent** | An `ATZInteraction` notify fires         |

![SCREENSHOT](images/blueprints_SCREENSHOT_1.png)

These can be used like any Blueprint dispatcher:
```blueprint
Bind Event to OnAnimationStart
→ Play Sound / Trigger Logic / etc.
```

---

## Character Interface (`ATZCharacterInterface`)

To receive zone-related callbacks directly in your Blueprint character, implement the `ATZCharacterInterface`.

### How to implement

1. Open your character Blueprint.
2. Add `ATZCharacterInterface` under **Class Settings** → **Interfaces**.
3. Implement any of the following events:

### Available Interface Events

- `OnAnimTriggerEnter(Zone)`
- `OnAnimTriggerExit(Zone)`
- `OnAnimTriggerQueueEnter(Zone)`
- `OnAnimTriggerQueueExit(Zone)`
- `OnAnimTriggerAnimationStart(Zone)`
- `OnAnimTriggerAnimationEnd(Zone)`
- `OnAnimTriggerInteraction(Zone, InteractionTag)`

![SCREENSHOT](images/blueprints_SCREENSHOT_2.png)

---

## Manual Triggering (Recommended Usage)

If you're using **Manual** trigger mode, store the passed zone and call `Trigger Zone Interact` on input.

![SCREENSHOT](images/blueprints_SCREENSHOT_3.png)

---

## Other Zone Functions

You can also call:

- `Block Movement` / `Unblock Movement`
- `Block Rotation` / `Unblock Rotation`
- `Save State` / `Load State`

These are useful if you want precise control via Blueprints.

![SCREENSHOT](images/blueprints_SCREENSHOT_4.png)

---

➡️ Next: [Advanced Features](advanced.md)
