# 📘 Blueprint Function Reference

This page lists all Blueprint-accessible functions provided by SaveKit Lite, grouped by category.

## 🔹 Category: Save Kit → Slots

### `GetExistingSaveSlots()`
- Returns: `FString[]`
- Description: Lists all save slot names found in the save directory.


![GetExistingSaveSlots](images/Node_GetExistingSaveSlots.png)


### `GetSaveSlotInfos()`
- Returns: `FSaveSlotInfo[]`
- Description: Returns metadata for all existing save slots (slot name, save time, save version).


![GetSaveSlotInfos](images/Node_GetSaveSlotInfos.png)


### `LoadSaveMetadata(SlotName)`
- Input: `FString SlotName`
- Returns: `FSaveSlotInfo`
- Description: Returns metadata only (does NOT load state).  
  See [UI Integration](ui.md) for usage in slot previews.


![LoadSaveMeta](images/Node_LoadSaveMetadata.png)

---

## 🔹 Category: Save Kit

### `SaveGame(SlotName, SaveVersion)`
- Input: `FString SlotName`, `int32` `SaveVersion` (optional)
- Description: Saves all actors with a Saveable component to the specified slot.


![SaveGame](images/Node_SaveGame.png)


### `LoadGame(SlotName)`
- Input: `FString SlotName`
- Description: Loads and applies saved actor data from the specified slot.


![LoadGame](images/Node_LoadGame.png)


---

## 🔹 Category: Save Kit → Saveable (component functions)

### `SetVariable(Name)`
- Description: Sets a string variable in the Saveable component.


![SetVariable](images/Node_SetVariable.png)


### `GetVariable(Name)`
- Description: Gets the string value of a saved variable.


![GetVariable](images/Node_GetVariable.png)


### `GetVariableAsInt(Name)`
- Description: Parses the variable’s value as an integer and returns it.


![GetVariableAsInt](images/Node_GetVariableAsInt.png)


### `HasVariable(Name)`
- Description: Checks whether a variable with the specified name exists.


![HasVariable](images/Node_HasVariable.png)


### `IncrementVariable(Name)`
- Description: Adds the specified amount to the variable’s value (as number).


![IncrementVariable](images/Node_IncrementVariable.png)


### `RemoveVariable(Name)`
- Description: Removes the variable from saved state.


![RemoveVariable](images/Node_RemoveVariable.png)


---

### 🧱 Save Slot Info Object

### `Init(SlotName, Time, Version)`
- Description: Initializes a SaveSlotInfoObject with name, time and version.


![Init](images/Node_Init.png)


---

## 📦 Notes

All SaveKit Lite functions are available in Blueprints via context-sensitive search, and can be used in:

- UMG widgets (`ListView`, `Button`, `Text`)
- Level, Actor, or GameMode Blueprints
- Custom save/load UI logic
