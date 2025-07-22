# Getting Started

This guide shows how to quickly set up and use the **Animation Trigger Zones** plugin entirely in Blueprints — no C++ required.

---

## Plugin Installation

1. Open your Unreal Engine project.
2. Go to `Edit` → `Plugins`.
3. Search for **Animation Trigger Zones**.
4. Enable the plugin.
5. Restart the editor to apply changes.

---

## Adding a Trigger Zone to Your Level

1. Open the desired map in your project.
2. Select an existing actor in your level (or create a new empty Actor).
3. In the **Details** panel, click **Add Component** → search for `AnimTriggerZoneComponent` and add it.

🎯 This component handles all animation triggering logic and can be configured via the Details panel.

---

## Assigning Animations

1. Select the `AnimTriggerZoneActor` in the scene.
2. In the **Details** panel, go to the `Animation` category.
3. Add one or more `AnimMontage` assets to the `Montages` array.

📌 If you use **entry points**, montages should be assigned to those components instead. Otherwise, use this array directly.

---

## Configuring the Zone Shape

In the `Shape` category:

1. Choose the zone shape:
   - `Box`
   - `Sphere`
   - `Capsule`
2. Set the corresponding dimensions:
   - `BoxExtent`
   - `SphereRadius`
   - `CapsuleRadius` and `CapsuleHalfHeight`

<!-- PLACEHOLDER: SCREENSHOT_SHAPE_SETTINGS -->

---

## Choosing Trigger Mode

In the `Animation` category:

- **Trigger Mode**  
  - `Auto`: plays animation automatically when an actor enters the zone.  
  - `Manual`: requires calling the zone manually from Blueprint.

- **Repeat Mode**  
  - `Once`: plays once per actor.  
  - `LoopWhileInside`: keeps playing in a loop while the actor stays inside.  
  - `RepeatOnReenter`: plays every time the actor enters the zone.

---

## Manual Trigger (Blueprint Example)

If you're using **Manual** mode:

1. Implement the `OnAnimTriggerEnter` event from `ATZCharacterInterface` in your character Blueprint.
2. Store the passed zone reference in a variable.
3. On button press, call `Trigger Zone Interact` and pass `Self` as the actor.

<!-- PLACEHOLDER: SCREENSHOT_TRIGGER_ZONE_INTERACT -->

Example Blueprint flow:

```blueprint
Event OnAnimTriggerEnter (Zone)
→ Set MyCurrentZone = Zone

Event OnButtonPressed
→ MyCurrentZone → Trigger Zone Interact (Self)
```

---

## Testing the Setup

1. Click **Play** to test the level.
2. Move your character into the zone:
   - In `Auto` mode, animation should start automatically.
   - In `Manual` mode, call `Trigger Zone Interact` from Blueprint to trigger it.

💡 Enable `Enable Debug Draw` in the zone settings to see the zone shape and entry point directions during gameplay.

---

➡️ Continue to [Trigger Zone Settings](trigger-zone.md) for detailed parameter explanations.