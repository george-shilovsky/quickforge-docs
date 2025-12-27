# 📚 Reference

This is a complete reference for all parameters, structures, functions, and enums used in **Smart Cone Trace**.

---

## 🧱 Component Parameters

| Name                     | Type                   | Default     |
|--------------------------|------------------------|-------------|
| `Interval`               | `float`                | `0.25`      |
| `Length`                 | `float`                | `200.0`     |
| `AngleDegrees`           | `float`                | `40.0`      |
| `TraceChannel`           | `ETraceTypeQuery`      | `TraceTypeQuery1` |
| `ActorsToIgnore`         | `Array<Actor>`         | `[]`        |
| `RequiredClass`          | `Class<Actor>`         | `None`      |
| `RequiredTags`           | `Array<Name>`          | `[]`        |
| `RequiredInterface`      | `Class<Interface>`     | `None`      |
| `bMultiHit`              | `bool`                 | `false`     |
| `bIgnoreSelf`            | `bool`                 | `true`      |
| `DebugMode`              | `EConeDebugMode`       | `None`      |
| `DebugDuration`          | `float`                | `1.0`       |
| `StepSize`               | `float`                | `40.0`      |
| `BoxDepth`               | `float`                | `60.0`      |
| `ToleranceDegrees`       | `float`                | `2.0`       |
| `bUseComponentTransform` | `bool`                 | `true`      |
| `bCheckVisibility`       | `bool`                 | `false`     |
| `VisibilityChannel`      | `ETraceTypeQuery`      | `TraceTypeQuery1` |
| `VisibilityOriginMode`   | `EVisibilityOriginMode`| `ScreenPoints`|
| `VisibilityBoundsScale`  | `float`                | `0.95`      |

**ℹ️ Note:** `ActorsToIgnore` only accepts actors that are already placed in the level.  
[Learn more about this limitation →](usage.md#i-about-actorstoignore)

---

## 📦 Struct: `FSmartConeTraceResult`

| Field          | Type               | Description                         |
|----------------|--------------------|-------------------------------------|
| `bDidHit`      | `bool`             | `true` if anything was hit          |
| `Hits`         | `Array<HitResult>` | All valid hits (filtered)           |
| `HitActors`    | `Array<Actor>`     | All valid hit actors                |
| `ClosestHit`   | `HitResult`        | Closest valid hit                   |
| `VisibleActors`| `Array`            | Actors that passed the visibility (line-of-sight) check. Empty if `bCheckVisibility` is false.|

---

## 🧰 Blueprint Function: `ConeTraceByChannel()`

Returns: `FSmartConeTraceResult`  
Defined in: `SmartConeTraceLib`

| Parameter             | Type                    | Required | Description                         |
|-----------------------|-------------------------|----------|-------------------------------------|
| `WorldContextObject`  | `Object`                | ✅       | Usually `self`                      |
| `Start`               | `Vector`                | ✅       | Origin point of the cone            |
| `Direction`           | `Vector`                | ✅       | Direction the cone faces            |
| `Length`              | `float`                 | ✅       | How far the cone extends            |
| `AngleDegrees`        | `float`                 | ✅       | Half-angle of the cone in degrees   |
| `TraceChannel`        | `ETraceTypeQuery`       | ✅       | Object types to trace               |
| `ActorsToIgnore`      | `Array<Actor>`          | ❌       | Skip these actors during trace      |
| `RequiredClass`       | `Class<Actor>`          | ❌       | Only include actors of this class   |
| `RequiredTags`        | `Array<Name>`           | ❌       | Only include actors with these tags |
| `RequiredInterface`   | `Class<Interface>`      | ❌       | Only include actors implementing it |
| `bMultiHit`           | `bool`                  | ❌       | Whether to collect all hits         |
| `bIgnoreSelf`         | `bool`                  | ❌       | Whether to skip tracing the owner   |
| `DebugMode`           | `EConeDebugMode`        | ❌       | Visualize trace shapes              |
| `DebugDuration`       | `float`                 | ❌       | Time to display debug shapes        |
| `StepSize`            | `float`                 | ❌       | Distance between trace steps        |
| `BoxDepth`            | `float`                 | ❌       | Depth of each trace box             |
| `ToleranceDegrees`    | `float`                 | ❌       | Extra angular tolerance             |
| `bCheckVisibility`    | `bool`                  | ❌       | Enable line-of-sight checks         |
| `VisibilityOriginMode`| `EVisibilityOriginMode` | ❌       | Start point of visibility traces    |
| `VisibilityBoundsScale`| `float`                | ❌       | Scale of target bounds to trace against|

---

## 🔁 Timer Functions

Also in `SmartConeTraceLib`:

| Function | Description |
|---------|-------------|
| `StartConeTraceTimer(WorldContext, TargetActor, CallbackFunctionName, Interval, bLoop)` | Binds a Blueprint function to be called repeatedly on a timer. |
| `StopConeTraceTimer(WorldContext, TargetActor)` | Stops the timer for the given actor. |

---

## 🔍 Helper Functions

All helper functions work with the `FSmartConeTraceResult` struct.

| Function                          | Return Type     | Description                        |
|-----------------------------------|------------------|------------------------------------|
| `GetClosestHitActor(Result)`      | `Actor`          | Returns the closest hit actor      |
| `GetFirstValidHitActor(Result)`   | `Actor`          | Returns the first hit actor        |
| `WasActorHit(Result, Actor)`      | `bool`           | `true` if that actor was hit       |
| `IsValidHit(Result)`              | `bool`           | `true` if any valid hit exists     |
| `GetHitActorsByClass(Result, Class)` | `Array<Actor>` | Filters hit actors by class        |
| `GetVisibleActors(Result)`        | `Array<Actor>`   | Returns only actors that passed the visibility check|
| `IsActorVisible(Result, Actor)`   | `bool`           | Returns true if the actor is in the VisibleActors list|

---

## 🧾 Enum: `EConeDebugMode`

Used to control debug visualization.

| Value     | Description                               |
|-----------|-------------------------------------------|
| `None`    | No visual debug                           |
| `Basic`   | Hit lines and impact points               |
| `Full`    | Full cone shape: lines, boxes, points     |

---

## 🧾 Enum: `EVisibilityOriginMode`

Determines the starting point for visibility raycasts.

| Value         | Description                                                          |
|---------------|----------------------------------------------------------------------|
| `ScreenPoints`| Traces from the camera (Center + 4 corners). Best for "Player Vision"|
| `ScreenCenter`| Traces from the exact center of the screen (Crosshair)               |
| `ConeStart`   | Traces from the cone's origin. Best for "AI Vision" or sensors       |

---

Looking for real examples? Check out [Examples](examples.md) »
