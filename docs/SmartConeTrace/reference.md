# 📚 Reference

This is a complete reference for all parameters, structures, functions, and enums used in **Smart Cone Trace**.

---

## 🧱 Component Parameters

| Name                   | Type                     | Default     |
|------------------------|--------------------------|-------------|
| `Interval`             | `float`                  | `0.25`      |
| `Length`               | `float`                  | `200.0`     |
| `AngleDegrees`         | `float`                  | `40.0`      |
| `TraceChannel`         | `ETraceTypeQuery`        | `TraceTypeQuery1` |
| `ActorsToIgnore`       | `Array<Actor>`           | `[]`        |
| `RequiredClass`        | `Class<Actor>`           | `None`      |
| `RequiredTags`         | `Array<Name>`            | `[]`        |
| `RequiredInterface`    | `Class<Interface>`       | `None`      |
| `bMultiHit`            | `bool`                   | `false`     |
| `bIgnoreSelf`          | `bool`                   | `true`      |
| `DebugMode`            | `EConeDebugMode`         | `None`      |
| `DebugDuration`        | `float`                  | `1.0`       |
| `StepSize`             | `float`                  | `40.0`      |
| `BoxDepth`             | `float`                  | `60.0`      |
| `ToleranceDegrees`     | `float`                  | `2.0`       |
| `bUseComponentTransform` | `bool`                 | `true`      |

---

## 📦 Struct: `FSmartConeTraceResult`

| Field         | Type             | Description                         |
|---------------|------------------|-------------------------------------|
| `bDidHit`     | `bool`           | `true` if anything was hit          |
| `Hits`        | `Array<HitResult>` | All valid hits (filtered)         |
| `HitActors`   | `Array<Actor>`   | All valid hit actors                |
| `ClosestHit`  | `HitResult`      | Closest valid hit                   |

---

## 🧰 Blueprint Function: `ConeTraceByChannel()`

Defined in: `SmartConeTraceLib`  
Returns: `FSmartConeTraceResult`

### Required Inputs:
- `WorldContextObject` (usually `self`)
- `Start` — `Vector`
- `Direction` — `Vector`
- `Length` — `float`
- `AngleDegrees` — `float`
- `TraceChannel` — `ETraceTypeQuery`

### Optional Inputs:
- `ActorsToIgnore` — `Array<Actor>`
- `RequiredClass` — `Class<Actor>`
- `RequiredTags` — `Array<Name>`
- `RequiredInterface` — `Class<Interface>`
- `bMultiHit` — `bool`
- `bIgnoreSelf` — `bool`
- `DebugMode` — `EConeDebugMode`
- `DebugDuration` — `float`
- `StepSize` — `float`
- `BoxDepth` — `float`
- `ToleranceDegrees` — `float`

---

## 🔁 Timer Functions

Also in `SmartConeTraceLib`:

### `StartConeTraceTimer(WorldContext, TargetActor, CallbackFunctionName, Interval, bLoop)`
- Binds a Blueprint function to be called repeatedly on a timer.

### `StopConeTraceTimer(WorldContext, TargetActor)`
- Stops the timer for the given actor.

---

## 🔍 Helper Functions

Return values are based on `FSmartConeTraceResult`.

| Function                       | Return Type    | Description                        |
|--------------------------------|----------------|------------------------------------|
| `GetClosestHitActor(Result)`  | `Actor`        | Returns the closest hit actor      |
| `GetFirstValidHitActor(Result)` | `Actor`      | Returns the first hit actor        |
| `WasActorHit(Result, Actor)`  | `bool`         | `true` if that actor was hit       |
| `IsValidHit(Result)`          | `bool`         | `true` if any valid hit exists     |
| `GetHitActorsByClass(Result, Class)` | `Array<Actor>` | Filters hit actors by class |

---

## 🧾 Enum: `EConeDebugMode`

Used to control debug visualization.

| Value     | Description                               |
|-----------|-------------------------------------------|
| `None`    | No visual debug                           |
| `Basic`   | Hit lines and impact points               |
| `Full`    | Full cone shape: lines, boxes, points     |

---

Looking for real examples? Check out [Examples](examples.md) »
