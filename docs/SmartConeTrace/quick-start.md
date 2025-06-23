# 🚀 Quick Start

This guide will help you start using **Smart Cone Trace** in less than 2 minutes.

---

## 1. Enable the Plugin

1. Open your Unreal Engine project.
2. Go to `Edit > Plugins`.
3. Search for **Smart Cone Trace** and enable it.
4. Restart the editor if prompted.

![Plugin browser with Smart Cone Trace enabled](images/quick-start_SCREENSHOT_1.png)  
*Smart Cone Trace plugin enabled in the Plugins panel.*

---

## 2. Add the Component

1. Open any Actor Blueprint (like a character or AI pawn).
2. In the Components panel, click **Add Component** and choose **SmartConeTrace**.
3. Select it and adjust the settings in the Details panel:
   - `Interval` — how often the trace runs (e.g. every 0.25 seconds)
   - `Length` — how far the cone reaches
   - `AngleDegrees` — how wide the cone is

![Component added to Blueprint and settings panel](images/quick-start_SCREENSHOT_2.png)  
*SmartConeTrace component selected, with editable parameters like Interval and Angle.*

---

## 3. Handle the Result

1. In the Components panel, right-click the **SmartConeTrace** component.
2. Choose **Add Event → Add OnConeTraceResult**.

This creates an event node that fires every time the trace runs.

![Event node and handling logic in Blueprint](images/quick-start_SCREENSHOT_3.png)  
*A basic event setup using the OnConeTraceResult node to print the closest hit actor.*

---

## 4. Test It

1. Place the actor in the level.
2. Hit **Play**.
3. The cone will automatically trace and trigger the event.

If debug mode is enabled, you’ll see the trace shape, hit boxes, and impact points.

![In-game cone debug visualization](images/quick-start_SCREENSHOT_4.png)  
*Cone shape visualized in-game with debug mode set to Full.*

---

## ✅ Done!

You’re now using Smart Cone Trace in your Blueprint project.

Next:  
→ Learn how it works in [Usage](usage.md)  
→ See real examples in [Examples](examples.md)