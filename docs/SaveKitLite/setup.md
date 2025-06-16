## 🔧 Quick Start

To get started:

1. Add `Saveable` to any actor

![Saveable Component](images/SaveableComponent.png)

2. Use `Save Kit → SaveGame(SlotName)` and `LoadGame(SlotName)` Blueprint nodes

![Save/Load Nodes](images/SaveGameLoadGame.png)

3. ✅ Done! Your actor state is now persistent

---

# 🛠️ Setup – Adding Saveable

To enable saving on an actor, attach the `Saveable` component and configure it in the Details panel.

---

## 1. Add `Saveable` to your Actor

Open the Blueprint of any actor you want to save (e.g. character, chest, enemy).

- Click **Add Component**
- Choose `Saveable`

---

## 2. Configure the component

| Option            | Description                                       |
|-------------------|---------------------------------------------------|
| `Save Transform`  | Saves location, rotation, and scale               |
| `Variables To Save` | List of custom key-value string variables       |

> 🎯 These variables can later be updated dynamically at runtime and will persist through save/load.


![Saveable Component Settings](images/ChooseSaveable.png)

💡 Example of Variables To Save:
```plaintext
Variables To Save:
- Health
- IsDamaged
- Score
```
