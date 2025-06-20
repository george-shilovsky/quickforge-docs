# 🛠️ Usage Guide

This page explains how to use both the **SmartConeTraceComponent** and the **Blueprint function**.

---

## 🧱 Option 1: Using the Component

The easiest way to use the plugin is with the `SmartConeTraceComponent`.

### ✅ It runs automatically:
- No need to call anything manually.
- Traces at regular intervals using your chosen settings.
- Sends results via the `OnConeTraceResult` event.

📷 **[SCREENSHOT_1: Blueprint showing component + event node]**  
*Show the component in the Blueprint and the OnConeTraceResult event connected.*

---

### 🔧 Key Parameters (in Details panel)

| Parameter           | Description                                           |
|---------------------|-------------------------------------------------------|
| `Interval`          | How often the trace runs (in seconds)                |
| `Length`            | How far the cone reaches                             |
| `AngleDegrees`      | Width of the cone                                     |
| `TraceChannel`      | Which objects to detect (visibility, pawn, etc.)     |
| `RequiredClass`     | Only include actors of this class (optional)         |
| `RequiredTags`      | Only include actors with these tags (optional)       |
| `RequiredInterface` | Only include actors with this interface (optional)   |
| `bMultiHit`         | If true, collect all hits; otherwise, only the closest |
| `bIgnoreSelf`       | Skip tracing against the owner actor                 |
| `DebugMode`         | Visualize the trace (lines, boxes, impact points)    |

📷 **[SCREENSHOT_2: Component parameters in Details panel]**  
*Show the component settings expanded with some values filled.*

---

## ⚙️ Option 2: Using the Blueprint Function

You can also use `ConeTraceByChannel()` directly from any Blueprint.

### 🧠 Use it when:
- You want to trace manually (not on a timer)
- You want to control when and where the cone is cast
- You don’t need a component

📷 **[SCREENSHOT_3: Blueprint using ConeTraceByChannel node]**  
*Show the function node with inputs like Start, Direction, Length, etc.*

---

### 🧪 Enabling Debug View

Set `DebugMode` to:
- `Basic` — draw hit lines and impact points
- `Full` — draw full cone shape (boxes + hits + lines)

📷 **[SCREENSHOT_4: Debug mode in action]**  
*Show visual output in the editor: colored lines, box shapes, red dots on hits.*

---

## 📌 Output: FSmartConeTraceResult

Whether you use the component or the function, the result is the same:

- `HitActors` — array of all valid hit actors
- `ClosestHit` — the nearest hit (with full hit info)
- `bDidHit` — true if anything was hit

You can also use helper functions like:
- `GetClosestHitActor()`
- `WasActorHit()`
- `GetHitActorsByClass()`

📷 **[SCREENSHOT_5: Example of using result in Blueprint]**  
*Show result pin being used to print names or check if actor was hit.*

---

## 🧭 Use with AI or Abilities

Smart Cone Trace is great for:
- Enemy AI "vision cone"
- Detecting nearby players
- Area scan abilities or magical spells
- Obstacle detection ahead of a vehicle

📷 **[SCREENSHOT_6: Practical in-game usage like AI vision]**  
*Show actual use in game logic — AI scanning or detecting player.*

---

Next: Check out real-world [Examples](examples.md) »
