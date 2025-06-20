# 🎮 Examples

This page shows real use cases for Smart Cone Trace, using only Blueprints.

---

## 🧠 Example 1: AI Vision Cone

You want your enemy AI to detect the player when they enter a visible cone area in front of them.

### Setup

1. Open your AI character Blueprint.
2. Add a `SmartConeTraceComponent`.
3. Set these values:
   - `Interval` = `0.2`
   - `Length` = `1000`
   - `AngleDegrees` = `60`
   - `TraceChannel` = `Visibility`
   - `RequiredClass` = `Character` (optional)
   - `DebugMode` = `Full`

4. Use the `OnConeTraceResult` event.

📷 **[SCREENSHOT_1: AI Blueprint with component and event]**  
*Show the component and its event in use.*

---

### Blueprint Logic

In the event:

1. Use `GetClosestHitActor(Result)` to check for the player.
2. If the player is found, update AI blackboard or chase them.

📷 **[SCREENSHOT_2: Event checking for player and triggering alert]**  
*Show a branch checking the actor class and triggering some behavior.*

---

### Debug Output

You will see:

- Cone shape in pink
- Red dots at impact points
- Green lines for hits

📷 **[SCREENSHOT_3: In-game cone hitting the player]**  
*Show player standing in cone with debug visuals.*

---

## ✨ Example 2: Area Scan Ability

You want the player to scan the area in front of them (like a sonar pulse).

### Setup

1. In your player Blueprint, call `ConeTraceByChannel()` when pressing a key (e.g. "E").
2. Set inputs:
   - `Start` = `GetActorLocation`
   - `Direction` = `GetActorForwardVector`
   - `Length` = `1500`
   - `AngleDegrees` = `45`
   - `TraceChannel` = `Visibility`
   - `bMultiHit` = `true`
   - `DebugMode` = `Full`

📷 **[SCREENSHOT_4: Blueprint calling ConeTraceByChannel]**  
*Show function node connected to an input event.*

---

### Logic After Trace

1. Loop over `HitActors` and highlight them (outline, glow, etc.)
2. Play a sound or visual pulse.

📷 **[SCREENSHOT_5: Looping over actors and calling a custom event]**  
*Show a `For Each` node handling detected actors.*

---

### Optional: Add Tags or Interfaces

You can restrict what gets detected:

- Only actors with tag `"Scannable"`
- Or actors that implement a custom interface like `BPI_Scannable`

📷 **[SCREENSHOT_6: Using tag or interface filter in Details panel]**  
*Show `RequiredTags` or `RequiredInterface` filled in.*

---

## ✅ Summary

These examples show just a few ideas:

- AI detection (guards, creatures, turrets)
- Ability range checks (fire cones, ice bursts, sonar)
- Trap triggers and sensors
- Player field of view checks

Now it’s your turn — trace anything, filter everything, and build smart logic with just Blueprints.

Need more details? Return to [Usage](usage.md) or [Reference](reference.md).
