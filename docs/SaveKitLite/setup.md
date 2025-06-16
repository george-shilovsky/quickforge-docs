## 🚀 Quick Start

Getting started with **SaveKit Lite** takes just a few steps:

---

### 1. Add the `Saveable` Component

Open the Blueprint of any actor you want to save (e.g. character, item, enemy):

- Click **Add Component**
- Select `Saveable` from the list

![Saveable Component](images/SaveableComponent.png)

---

### 2. Use Blueprint Nodes to Save and Load

Use these nodes in any Blueprint:

- `Save Kit → SaveGame(SlotName)`
- `Save Kit → LoadGame(SlotName)`

![Save/Load Nodes](images/SaveGameLoadGame.png)

---

### 3. Done ✅  
Your actor’s state is now persistent between play sessions.

---

## 🛠 Setup — Configuring `Saveable`

Adjust these properties in the Details panel of your actor:

| Setting                | Description                                          |
|------------------------|------------------------------------------------------|
| `Save Transform`       | Saves actor's location, rotation, and scale         |
| `Variables To Save`    | Custom key-value string pairs for runtime data      |
| `Apply Control Rotation` | Restores controller yaw if the actor has one     |

![Saveable Component Settings](images/ChooseSaveable.png)

> 💡 Example `Variables To Save`:
```plaintext
Health
IsDamaged
Score
