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
3. In the **Details** panel, click **Add Component** → search for `AnimTriggerZone` and add it.

🎯 This component handles all animation triggering logic and can be configured via the Details panel.

---

## Assigning Animations

Animations are assigned through **ATZEntryPoint** components.

1. In the same actor, add at least one `ATZEntryPoint` as a **child** of the `AnimTriggerZone` component (via the component hierarchy).
2. Select the `ATZEntryPoint`.
3. In the **Details** panel, add one or more `AnimMontage` assets to the `Random Montage` array.

📌 `ATZEntryPoint` must be a **child of the `AnimTriggerZone`** in the component hierarchy. Otherwise, it will not be used at runtime.

📌 Even if you are not using entry-based movement, **you must have at least one ATZEntryPoint to provide montages**.  
Each entry point acts as a container for animations.

💡 You can add multiple entry points to offer variety or random selection.

---

## Optional: Adding Interaction Points

You can also use **ATZInteractionPoint** components to trigger additional logic during animations (e.g. grab, push, pick up):

1. Add one or more `ATZInteractionPoint` components as **children of the `AnimTriggerZone`**.
2. Assign a unique `Interaction Tag` in the Details panel.
3. In your animation, add a `ATZInteraction` notify and set the same tag.

⚠️ Just like entry points, **interaction points must be children of the AnimTriggerZone** component to function properly.

---

## Configuring the Zone Shape

In the `Shape` category of the `AnimTriggerZone`:

1. Choose the zone shape:
   - `Box`
   - `Sphere`
   - `Capsule`
2. Set the corresponding dimensions:
   - `Box Extent`
   - `Sphere Radius`
   - `Capsule Radius` and `Capsule Half Height`

<!-- PLACEHOLDER: SCREENSHOT_SHAPE_SETTINGS -->

---

## Choosing Trigger Mode

In the `Animation` category:

- **Trigger Mode**  
  - `Auto`: plays animation automatically when an actor enters the zone.  
  - `Manual`: requires calling the zone manually from Blueprint.

- **Repeat Mode**  
  - `Once`: plays once per actor.  
  - `Loop While Inside`: keeps playing in a loop while the actor stays inside.  
  - `Repeat On Reenter`: plays every time the actor enters the zone.

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

---

## Testing the Setup

1. Click **Play** to test the level.
2. Move your character into the zone:
   - In `Auto` mode, animation should start automatically.
   - In `Manual` mode, call `Trigger Zone Interact` from Blueprint to trigger it.

💡 Enable `Enable Debug Draw` in the zone settings to see the zone shape and entry point directions during gameplay.

---

➡️ Continue to [Trigger Zone Settings](trigger-zone.md) for detailed parameter explanations.