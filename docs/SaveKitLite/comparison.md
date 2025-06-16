# ⚖️ SaveKit Lite vs. Unreal Engine Save Game System

While Unreal Engine provides built-in Save Game functionality, **SaveKit Lite** is designed to make common save/load tasks simpler, faster, and entirely Blueprint-accessible — with no boilerplate setup.

---

## 🔍 Core Differences

| Feature                              | UE Save System      | SaveKit Lite             |
|--------------------------------------|----------------------|---------------------------|
| Requires custom SaveGame class       | ✅ Yes               | ❌ No (uses built-in type) |
| Actor transform saving               | ❌ Manual            | ✅ Built-in via flag       |
| Actor tag saving                     | ❌ Manual            | ✅ Automatic               |
| Variable saving logic               | ❌ Manual coding     | ✅ Built-in key-value        |
| Component-based setup                | ❌ No                | ✅ `Saveable` component    |
| Auto actor discovery in level        | ❌ No                | ✅ Uses `TActorIterator`   |
| UI metadata (time, version, slot)    | ❌ No                | ✅ Built-in structs        |
| Save versioning                      | ❌ Manual (code)     | ✅ Optional param in node  |
| Blueprint-only compatibility | ⚠️ Limited | ✅ Full support |
| Blueprint-only workflow              | ⚠️ Partially         | ✅ 100% supported          |

---

## 🎯 Use SaveKit Lite When You Want:

- Faster prototyping of save/load features
- A no-code, Blueprint-only workflow
- Automatic saving of transforms, variables, and tags
- UI integration with `ListView` or buttons
- Slot metadata and save version control

---

## ❗ When to Use Native SaveGame

If you need:

- Full control of serialized data structures
- Complex nested objects or UObject arrays
- Saving references to spawned actors or runtime instances
- Custom asynchronous systems at scale

Then native SaveGame + C++ may be better.

---

✅ For 90% of common use cases — SaveKit Lite is **faster, easier, and modular**.

💡 SaveKit Lite is fully compatible with UE SaveGame — you can mix both as needed.
Use C++ to extend or bridge advanced cases.