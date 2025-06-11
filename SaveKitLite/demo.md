# 🎮 Demo Level – Quick Start Walkthrough

The SaveKit Lite demo level is included to showcase the core features of the plugin in a live environment.

---

## 🧩 What's Included

- A simple level with interactable actors
- Save/load logic bound to UI buttons
- Real-time updates to transform and variables
- UI `ListView` to preview existing save slots

---

## 🛠 How to Use

1. **Enable the plugin** in your UE5 project
2. **Open the demo map** located under:
   ```
   Plugins/SaveKitLite/Content/Maps/DemoLevel.umap
   ```
3. Press **Play** to test:
   - Move the character or actor
   - Click Save
   - Move again
   - Click Load to restore

---

## 🧠 Features Demonstrated

| Feature                | Demonstrated? |
|------------------------|----------------|
| Saveable      | ✅              |
| Variable updates       | ✅              |
| Actor transform saving | ✅              |
| Tags preservation      | ✅              |
| Save slot UI           | ✅              |
| Metadata preview       | ✅              |

---

> 💡 Use this demo as a starting point to implement your own save/load system by copying logic into your levels or UI widgets.


---

## 🛠 How to Modify

To adapt the demo to your game:

- Copy the demo UI widgets (e.g. `WBP_SaveMenu`) to your project
- Replace actor Blueprints with your own and attach `Saveable`
- Customize save/load buttons and hook up nodes from SaveKit
- 💡 To showcase variable saving, call `SetVariable` before `SaveGame`