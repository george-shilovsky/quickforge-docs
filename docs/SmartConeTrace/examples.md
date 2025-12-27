# 🧪 Interactive Demo – See Smart Cone Trace in Action

See Smart Cone Trace in a real-world Blueprint setup — using actor components, trace functions, filtering, and debug visualization — all in one quick, hands-on demo.

---

## ▶️ Watch the Demo

🎥 <a href="https://youtu.be/DdDTlY605dc" target="_blank">Watch on YouTube V1.0</a>

🎥 <a href="https://youtu.be/w6bPGncPn-c" target="_blank">Watch on YouTube V1.1</a>

In this demo, you'll see:

- A tank actor with a `SmartConeTrace` component that detects the player
- A static sensor actor using the `ConeTraceByChannel()` function manually
- The player actor also using SmartConeTrace to detect other actors
- Live tag, class, and interface filtering in action
- Full debug visualization of cone shape and hit results
- All logic implemented in Blueprints — no C++ needed

---

## 🎮 Play the Demo (Windows)

Try the exact project shown in the video:

🔗 <a href="https://drive.google.com/file/d/10DbIip9hQaxYcFPoechDhvckbUmndk4L/view?usp=sharing" target="_blank">Download Demo Build (.zip)</a>

Includes:

- Third-person level with three working cone trace actors:
  - A tank with automatic forward detection
  - A scanning sensor that reacts to the player
  - The player showing trace results with different filters
- Real-time debug drawing and UI feedback

📌 Just unzip and run `SmartConeTraceEx.exe`.

---

## 🧱 Blueprint Examples – Learn by Inspecting

Download the project files and explore how each actor works:

🔗 <a href="https://drive.google.com/drive/folders/1yq24qvmLCNEyeOrcuhkoNv97G7AKprcg?usp=sharing" target="_blank">Download Sample Project</a>

You’ll get:

- Tank, Sensor, and Player Blueprints using cone trace
- Both component-based and function-based setups
- Example filters: `RequiredTags`, `RequiredClass`, `RequiredInterface`
- On-screen UI: `WBP_TraceInfo` widget
- Ready to copy and adapt

---

## 🎮 Real-World Usage Examples

Smart Cone Trace is flexible and can be used in many gameplay scenarios:

### 🧠 AI Vision

Give enemies, drones, or creatures a cone-based field of view.  
Trigger alerts or behaviors when the player enters their line of sight.

- Attach the component to AI characters
- **Use `bCheckVisibility` to prevent seeing through walls**
- Detect only specific actors (e.g. Characters with tag `"Player"`)
- React through `OnConeTraceResult` in Blueprint

---

### ✨ Area Scan Ability

Let the player scan an area in front of them on command (like a pulse).

- Call `ConeTraceByChannel()` on key press
- Highlight found objects
- Filter results by tag or interface

---

### 🔥 Ability Zones

Use cone-shaped traces for flame breath, ice blasts, or shout attacks.

- Hit multiple enemies with `bMultiHit`
- Sync VFX and SFX with the actual trace volume
- Trigger effects only for valid targets

---

### 🧩 Traps & Sensors

Use cone tracing in level geometry to detect intruders or activate traps.

- Automatically trace at intervals
- Combine with trigger boxes, cameras, or events

---

## ✅ Key Features Demonstrated

| Feature                          | Covered |
|----------------------------------|---------|
| Component-based cone tracing     | ✅       |
| Manual function-based tracing    | ✅       |
| Tag/class/interface filtering    | ✅       |
| Closest hit and multi-hit logic  | ✅       |
| Real-time debug visualization    | ✅       |
| On-screen hit display (UI)       | ✅       |
| Pure Blueprint implementation    | ✅       |

---

> 🧩 Whether you're building AI vision, scanning tools, trap systems, or gameplay abilities — Smart Cone Trace gives you precision control with simple Blueprint logic.