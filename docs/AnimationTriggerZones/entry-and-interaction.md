# Entry Points & Interactions

This section explains how to position actors before animations and how to trigger logic using animation notifies.

---

## Entry Points (`ATZEntryPointComponent`)

Entry points define where an actor should go before playing their animation.

### How to add an Entry Point

1. Select the actor that contains your `AnimTriggerZoneComponent`.
2. In the **Details** panel, click **Add Component** → search for `ATZEntryPointComponent`.
3. Position the new component where the actor should appear.
4. Rotate the arrow to face the desired direction.

<!-- PLACEHOLDER: SCREENSHOT_ADD_ENTRY_POINT -->

### Zone settings

- Enable `Use Entry Points` in the zone.
- Choose **Entry Mode**:
  - `Teleport`: actor instantly moves to the point.
  - `Move To`: actor walks to the point using AI navigation.

### Random Animation per Entry

Each entry point can define its own animation list:

- Use the `RandomMontage` array inside the `ATZEntryPointComponent`.
- If left empty, the zone will use the global `Montages` array.

📌 Only one actor can occupy each entry point at a time. If all are full, the actor is added to the queue (if enabled).

---

## Interaction Points (`ATZInteractionPointComponent`)

Interaction points allow animation notifies to trigger logic in Blueprint.

### How to use

1. Add a component `ATZInteractionPointComponent` to the same actor that holds your `AnimTriggerZoneComponent`.
2. Set the **Interaction Tag** (e.g., "Use", "Fire", "Sit").
3. Open your AnimMontage and add an AnimNotify of type `ATZInteraction`.
4. In the notify, enter the same tag.

When the notify fires, the zone will find the matching interaction point and call its event.

### Blueprint Event

Use the `OnInteractionTriggered` event to hook up logic.

```blueprint
Event OnInteractionTriggered (Instigator)
→ Run your custom Blueprint logic
```

📌 You can also use the `OnInteractionTriggeredEvent` on the zone itself to receive tagged notifies globally.

<!-- PLACEHOLDER: SCREENSHOT_NOTIFY_TAG -->

---

## Interaction Types

Each `ATZInteractionPoint` also has a **Type** field (enum):

- `Activate` — for use or switch-type logic.
- `Pickup` — for items or grabbing.
- `Custom` — anything else.

You can branch on this in Blueprints for different behaviors.

---

➡️ Next: [Blueprint Events & Interfaces](blueprints.md)