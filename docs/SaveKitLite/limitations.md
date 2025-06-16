# ⚠️ Limitations & Best Practices

While SaveKit Lite is powerful and easy to use, it's important to understand its design boundaries.

---

## ❌ What is NOT supported

| Unsupported Feature         | Why?                                      |
|-----------------------------|-------------------------------------------|
| Saving UObject references   | Can't be serialized as text safely        |
| Arrays of components        | No automatic serialization available      |
| Blueprint-only dynamic spawning | Relies on actor names only — dynamically spawned actors are not recreated |
| Level streaming             | SaveKit Lite is level-instance-based only |

---

## 🧠 Best Practices

- ✅ Ensure each actor has a **unique name** in the level
- ✅ Use `VariablesToSave` for any dynamic state that isn't stored in properties
- ✅ If you need to save complex data — break it into string tokens
- ✅ For objects spawned at runtime — consider recreating them manually on Load
- ✅ Use consistent slot naming (e.g., ``AutoSave``, ``Quick1``, ``Checkpoint``)
- ✅ Don't rely on object references — instead store IDs or lookup keys
- ✅ When using `SaveGame` variables, prefer basic types (strings, numbers, bools)

---

## 🔧 Suggestions

🧭 These advanced needs are outside the scope of SaveKit Lite:

- World-level saving across maps → use GameInstance or a wrapper
- Custom object handling → extend Saveable with your logic
- Large game state persistence → look into full save systems or Pro-tier solutions



💡 Need advanced serialization? Use custom C++ logic or integrate formats like JSON for full control.