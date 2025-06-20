# 🛠️ Usage Guide

This page explains how to use:

- `SmartConeTraceComponent` — the automatic way
- `ConeTraceByChannel()` — the manual Blueprint function
- All result fields and helper functions

No C++ required — everything is Blueprint-ready.

---

## 🧱 Using the Component

Add the `SmartConeTraceComponent` to any actor.

It will automatically perform a cone trace every few seconds and call the event `OnConeTraceResult`.

📷 **[SCREENSHOT_1: Blueprint with the component and event]**  
*Show a Blueprint with the component added and OnConeTraceResult in the Event Graph.*

---

### 🔧 Component Parameters

All settings can be adjusted in the Details panel.

| Property             | Description |
|----------------------|-------------|
| `Interval`           | How often to perform the trace (in seconds). Set to `0` to disable automatic tracing. |
| `Length`             | How far the cone reaches. |
| `AngleDegrees`       | Width of the cone in degrees (spread). |
| `TraceChannel`       | What object types to trace (e.g. Visibility, Pawn). |
| `ActorsToIgnore`     | Optional list of actors to skip during trace. |
| `RequiredClass`      | Only include hits with this actor class (or child classes). |
| `RequiredTags`       | Only include actors that have any of these tags. |
| `RequiredInterface`  | Only include actors that implement this Blueprint interface. |
| `bMultiHit`          | If `true`, collect all valid hits. If `false`, only use the closest hit per step. |
| `bIgnoreSelf`        | Skip tracing against the owner actor. Usually `true`. |
| `DebugMode`          | Draw the cone in the world (lines, boxes, hit points). Options: `None`, `Basic`, `Full`. |
| `DebugDuration`      | How long to keep the debug visuals on screen (in seconds). |
| `StepSize`           | Distance between each box trace. Smaller = smoother cone. |
| `BoxDepth`           | Length of each individual box trace. |
| `ToleranceDegrees`   | Extra angle margin to accept hits slightly outside the cone. |
| `bUseComponentTransform` | If `true`, the trace starts from the component's position and direction. If `false`, uses the actor’s transform. |

📷 **[SCREENSHOT_2: Details panel with all properties visible]**  
*Show the component selected in the Details panel with some example values.*

---

## 📘 Result Event: `OnConeTraceResult`

This event is triggered after each trace (if interval > 0). It gives you a `SmartConeTraceResult` struct.

---

### 📦 SmartConeTraceResult Fields

| Field          | Type             | Description |
|----------------|------------------|-------------|
| `bDidHit`      | `bool`           | `true` if anything was hit. |
| `Hits`         | `Array<HitResult>` | All filtered hits. |
| `HitActors`    | `Array<Actor>`   | All valid actors that were hit. |
| `ClosestHit`   | `HitResult`      | The closest valid hit among all steps. |

📷 **[SCREENSHOT_3: Using result in Blueprint — print closest actor]**  
*Show Blueprint logic printing the name of the closest actor if any.*

---

## ⚙️ Using the Blueprint Function

If you want to trace manually, use `ConeTraceByChannel()` from `SmartConeTraceLib`.

It’s perfect for:

- One-time checks (e.g. on key press)
- Tracing from any point and direction
- Custom cone logic

📷 **[SCREENSHOT_4: Blueprint with ConeTraceByChannel node]**  
*Show the function in use with inputs like Start, Direction, etc.*

---

### 🧰 Function Inputs

Same parameters as the component, but passed directly into the function:

- `Start` — starting location of the cone
- `Direction` — direction the cone is facing
- All other parameters match the component (see table above)

You can get `Start` and `Direction` using nodes like:
- `Get Actor Location`
- `Get Forward Vector`
- `Get Component Location`

---

### 🔬 Debug Modes

| Debug Mode | Description |
|------------|-------------|
| `None`     | No visuals |
| `Basic`    | Lines + hit points |
| `Full`     | Boxes, lines, hit points (most detailed) |

📷 **[SCREENSHOT_5: Visual debug output in Full mode]**  
*Show in-game view with boxes, red dots, and debug cone.*

---

## 🧠 Helper Functions

You can use these helper functions from `SmartConeTraceLib` to work with the result:

| Function | What it does |
|----------|---------------|
| `GetClosestHitActor(Result)` | Returns the actor from `Result.ClosestHit`, or `null` |
| `WasActorHit(Result, Actor)` | Returns `true` if the given actor is in the hit list |
| `GetFirstValidHitActor(Result)` | Returns the first actor from the `HitActors` array |
| `GetHitActorsByClass(Result, Class)` | Returns all actors in `HitActors` that match the class |
| `IsValidHit(Result)` | Returns `true` if `Result.bDidHit` is `true` |

📷 **[SCREENSHOT_6: Blueprint calling GetClosestHitActor]**  
*Show usage of helper node to get actor and do something with it.*

---

Continue to [Reference](reference.md) for a technical list of parameters and return types.

Or jump to [Examples](examples.md) to see real use cases.
