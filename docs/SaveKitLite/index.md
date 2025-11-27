# 🧠 SaveKit Lite – Easy Blueprint Save System for UE5 (C++ Backend)

**SaveKit Lite** is a minimalist save/load system for Unreal Engine 5 with full Blueprint support. Implemented in C++, designed for easy use in Blueprints.

🔗 <a href="https://fab.com/s/1c043632008e" target="_blank">Available on Unreal Engine Marketplace</a> – get the plugin, leave a review, and support future development!

It allows you to save and load:

- 🎮 Actor transform (location, rotation, scale)
- 🧠 Custom string variables (like score, health, state)
- 🏷️ Actor tags and properties marked as `SaveGame`
> 💡 **Why save actor tags?** Tags can be used to categorize actors (e.g., `Enemy`, `Loot`, `Checkpoint`) and drive gameplay logic. Saving them ensures that gameplay-relevant identifiers like quest objectives, interactables, or triggers remain intact after loading.

- 🔐 **StableId support (v1.1+)** — optional persistent ID for cross-level loading 
- 💾 Metadata about save slots for UI display

---

## 💡 Why SaveKit Lite?

Unlike Unreal Engine's native Save Game system, SaveKit Lite gives you:

- 🧩 Actor-level saving with no custom classes
- 🔁 Built-in transform & tag support
- 📦 Key-value variable system for runtime data
- 📊 Metadata for UI display (slot name, version, timestamp)
- 🎯 Built in C++, but used entirely via Blueprints – no coding required

Want to know more? See the [Comparison with UE Save System](comparison.md) *(this file is part of the documentation bundle)*

---

> 📦 *SaveKit Lite is designed to be simple and extendable — ideal for indie projects, prototyping, and modular virtual world systems.*