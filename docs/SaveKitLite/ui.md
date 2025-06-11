# 🖼️ UI Integration – Displaying Save Slots

SaveKit Lite allows you to display available save slots in a user interface using standard Blueprint nodes.

You can:

- Show all existing save slots (by name)
- Retrieve and display metadata (save time, version)
- Load selected slots from the UI

---

## 📂 1. Show Available Save Slots

Use the node:

```
Save Kit → Slots → GetExistingSaveSlots()
```


![GetExistingSaveSlots node](images/Node_GetExistingSaveSlots.png)


This returns an array of `FString` slot names. You can use this to populate a `ListView`, combo box, or buttons dynamically.

---

## 🧠 2. Get Metadata for Each Slot

Use:

```
Save Kit → Slots → GetSaveSlotInfos()
```


![GetSaveSlotInfos node](images/Node_GetSaveSlotInfos.png)


This returns an array of `FSaveSlotInfo` structs with:

| Field         | Type       | Description                      |
|---------------|------------|----------------------------------|
| `SlotName`    | `FString`  | Save slot name                   |
| `SaveTime`    | `FDateTime`| Timestamp when the slot was saved|
| ```SaveVersion``` | `int32`    | Format or version indicator      |

Useful for building save/load menus with detailed information.

### 📦 Blueprint Example – Populate ListView

Use this logic to populate a ListView with metadata:


![Populate ListView](images/UI_LoadList_WithMetadata.png)


---

## 🧱 3. Display Info in List Entry

Each ListView item can use a `SaveSlotInfoObject` to display save name, time, and version.

Below is a full example that:

- Displays the save slot name
- Formats and shows the save time using `FormatText`
- Prepends version number like `v1`


![Display slot info in List Entry](images/UI_ListItem_DisplayDetails.png)


*Blueprint setup for `OnListItemObjectSet` inside a ListView entry widget.*

Make sure your widget implements `UserObjectListEntry`, which allows binding metadata to list items.


## 🧾 4. Load Metadata for Selected Slot

Use:

```
Save Kit → Slots → LoadSaveMetadata(SlotName)
```


![LoadSaveMetadata node](images/Node_LoadSaveMetadata.png)


Returns a `SaveSlotInfo` struct for the selected slot. Use it when you want to preview a slot before loading.

---

## 📘 5. Additional Nodes

These nodes are used to build the save/load UI:

- `GetExistingSaveSlots()`
- `GetSaveSlotInfos()`
- `LoadSaveMetadata(SlotName)` → returns metadata
- `LoadGame(SlotName)` → loads the selected save

You can use these in UMG widgets, buttons, or combo boxes.

---

## 💡 Tips

- Sort slots by `SaveTime` to show newest first
- Format `SaveTime` as ``"dd.MM.yyyy HH:mm"`` for better readability
- Use ``AutoSave`` or ``Profile_1`` as consistent slot names
