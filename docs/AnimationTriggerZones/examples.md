# 🧪 Interactive Demo – See Animation Trigger Zones in Action

See Animation Trigger Zones in a real-world Blueprint setup — with entry points, interaction notifies, looping logic, and queue management — all in one hands-on demo.

---

## ▶️ Watch the Demo

🎥 <a href="https://www.youtube.com/watch?v=52jrX-DKJP0&ab_channel=QuickForgeStudio" target="_blank">Watch on YouTube</a>

In this demo, you'll see:

- Trigger zones that play animation montages when actors enter them
- Smart positioning via Entry Points with teleport and MoveTo modes
- Looping animations while inside the zone
- Queued access when all entry points are occupied
- Interaction Points triggered via animation notifies
- Full debug visualization of entry and interaction markers
- All logic implemented in Blueprints — no C++ needed

---

## 🎮 Play the Demo (Windows)

Try the exact project shown in the video:

🔗 <a href="https://drive.google.com/file/d/1dSQSaZPafZ1glhUedIkX72YkeCiQ8DuT/view?usp=sharing" target="_blank">Download Demo Build (.zip)</a>

Includes:

- Third-person scene with multiple interactive trigger zones:
  - Teleport to animation points
  - Smooth MoveTo behavior with rotation
  - Playback of randomized animation montages
- Entry queue handling with wait timers
- Blueprint UI feedback and debug drawing

📌 Just unzip and run `AnimTriggerDemo.exe`.

---

## 🧱 Blueprint Examples – Learn by Inspecting

Download the full project and explore how each component works:

🔗 <a href="https://drive.google.com/drive/folders/1xabRRmCCMyXJPBheWHOv7clySYGkrfmq?usp=sharing" target="_blank">Download Sample Project</a>

You’ll get:

- Zones with different shapes: box, sphere, capsule
- Configurable trigger modes: Auto, Manual, Loop
- EntryPoint and InteractionPoint examples
- Character interface integration for queue and interaction events
- Example UI feedback widgets

📌 **Note**: Due to licensing restrictions, some original animation assets were removed from the sample project. You can easily replace them with your own animation montages or those available from the Marketplace.

---

## 🎮 Real-World Usage Examples

Animation Trigger Zones are flexible and ideal for many gameplay scenarios:

### 🛑 Contextual Interactions

Trigger animations when a player enters an area near a workstation, door, or object.

- Use EntryPoints for precise positioning and orientation
- Choose from randomized animation montages
- Trigger via overlap or manual Blueprint call

---

### 🔁 Looping Idle Animations

Keep NPCs animating while they remain inside a zone.

- Enable `LoopWhileInside` mode
- Automatically stop when they leave or move

---

### ⏳ Entry Queues for Crowded Zones

Limit the number of actors using a trigger zone at once.

- Enable queue with delay timers
- Use events `OnQueueEnter` and `OnQueueExit` for custom logic
- Automatic handling of entry point availability

---

### 🎬 Synchronized Cutscenes

Teleport or move actors to exact positions and trigger animations in sequence.

- Use `Teleport` or `MoveTo` entry modes
- Smooth rotation and movement included
- Trigger from Blueprints via `TriggerZoneInteract()`

---

### 🔄 AnimNotify-Based Interactions

Fire logic from animations using `UAnimNotify_ATZInteraction`.

- Attach `ATZInteractionPointComponent` for precise locations
- Match tags in AnimNotify to trigger specific Blueprint events
- Support branching behavior via `InteractionType`

---

## ✅ Key Features Demonstrated

| Feature                             | Covered |
|-------------------------------------|---------|
| Entry points with positioning       | ✅       |
| Animation montage triggering        | ✅       |
| Manual and automatic trigger modes  | ✅       |
| Looping and once-per-visit modes    | ✅       |
| Tag/class/filter-based actor logic  | ✅       |
| Entry queue with delay handling     | ✅       |
| AnimNotify-triggered interactions   | ✅       |
| Full Blueprint support              | ✅       |
| Debug drawing for all components    | ✅       |

---

> 🧠 Whether you're building interactive scenes, cutscenes, AI idle zones, or synchronized animation events — Animation Trigger Zones gives you precision and flexibility using only Blueprint logic.
