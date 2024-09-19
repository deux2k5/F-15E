---

# F-15E Modifications

Welcome to the **F-15E Modifications** repository! This project provides two mods for DCS World that enhance the F-15E experience:

1. **F-15E.lua Weapons Mod**: Unlocks all weapons and pods for the F-15E.
2. **NCTR.lua Mod**: Expands the Non-Cooperative Target Recognition (NCTR) capabilities to include additional aircraft, including modded and newly released ones.

---

## Table of Contents

- Introduction
- Mods Description
  - F-15E.lua Weapons Mod
  - NCTR.lua Mod
- Installation
  - F-15E.lua Weapons Mod Installation
  - NCTR.lua Mod Installation
- Understanding NCTR.lua Mod
  - How It Works
  - Adding or Removing Aircraft
  - Adjusting Detection Parameters
- Credits

---

## Introduction

These mods aim to enhance your F-15E experience in DCS World by unlocking additional weapons and improving the NCTR system to recognize more aircraft types, including modded and newly released aircraft.

**Note:** The F-15E.lua Weapons Mod will **break Integrity Check (IC)**. The NCTR.lua Mod, however, is designed to **not break IC** when installed correctly.

---

## Mods Description

### F-15E.lua Weapons Mod

- **File:** `F-15E.lua`
- **Purpose:** Unlocks all weapons and pods for the F-15E, giving you access to a wider array of armaments.
- **Installation Path:** `DCS World/CoreMods/aircraft/F-15E`
- **Integrity Check:** This mod will **break IC**.

### NCTR.lua Mod

- **File:** `NCTR.lua`
- **Purpose:** Enhances the NCTR system to include additional aircraft, including modded and newly released ones, without breaking IC.
- **Installation Path:** `Saved Games/DCS.openbeta/Config/F-15E`
- **Integrity Check:** This mod **does not break IC**.
- **Credits:** Thanks to **Brody** for the contributions.

---

## Installation

### F-15E.lua Weapons Mod Installation

1. **Backup Original File:**
   - Navigate to `DCS World/CoreMods/aircraft/F-15E`.
   - Locate the original `F-15E.lua` file and create a backup copy.

2. **Replace File:**
   - Copy the modded `F-15E.lua` file into the same directory, replacing the original.

3. **Integrity Check:**
   - Be aware that this mod will break IC on multiplayer servers that enforce it.

### NCTR.lua Mod Installation

1. **Create Config Folder (If Necessary):**
   - Navigate to `Saved Games/DCS.openbeta/Config`.
   - If the `F-15E` folder doesn't exist, create it.

2. **Place Mod File:**
   - Copy the `NCTR.lua` file into `Saved Games/DCS.openbeta/Config/F-15E`.

3. **Integrity Check:**
   - This mod is designed to not break IC, allowing you to use it on most multiplayer servers.

---

## Understanding NCTR.lua Mod

### How It Works

The `NCTR.lua` mod extends the F-15E's NCTR capabilities by modifying the `nctr_table`. This table contains entries for various aircraft, defining how the NCTR system recognizes them.

Each entry in the table follows this format:

```
nctr_table["Aircraft_Internal_Name"] = {"Display_Name", RCS_Value, Aspect_Angle}
```

- **Aircraft_Internal_Name:** The internal identifier used by DCS for the aircraft.
- **Display_Name:** The name that will be displayed on your radar screen.
- **RCS_Value (Radar Cross Section):** Represents the detectability of the aircraft. A higher value means the aircraft is easier to detect.
- **Aspect_Angle:** The maximum angle (in degrees) at which the aircraft can be detected by the NCTR system.

### Adding or Removing Aircraft

#### Adding an Aircraft

1. **Find the Internal Name:**
   - Locate the internal name of the aircraft you wish to add. This is often found in the mod's documentation or `lua` files.

2. **Create an Entry:**
   - Add a new line to the `nctr_table` with the appropriate values. For example:

     ```
     nctr_table["New_Aircraft_Internal_Name"] = {"Display_Name", RCS_Value, Aspect_Angle}
     ```

   - Replace `New_Aircraft_Internal_Name`, `Display_Name`, `RCS_Value`, and `Aspect_Angle` with the actual values.

#### Removing an Aircraft

- **Delete the Entry:**
  - Find the aircraft's entry in the `nctr_table` and delete the entire line.

### Adjusting Detection Parameters

#### RCS_Value (Radar Cross Section)

- **Purpose:** Determines how easily the aircraft can be detected.
- **Adjusting:**
  - Increase the value to make the aircraft more detectable.
  - Decrease the value to make it less detectable.
- **Example:**

  ```
  nctr_table["F-16C"] = {"F-16", 15.0, 45.0} -- More detectable
  nctr_table["F-16C"] = {"F-16", 5.0, 45.0}  -- Less detectable
  ```

#### Aspect_Angle

- **Purpose:** Defines the angle (in degrees) at which the aircraft can be detected.
- **Adjusting:**
  - Increase the angle to detect the aircraft over a wider area.
  - Decrease the angle to narrow the detection cone.
- **Example:**

  ```
  nctr_table["F-16C"] = {"F-16", 10.0, 60.0} -- Wider detection angle
  nctr_table["F-16C"] = {"F-16", 10.0, 30.0} -- Narrower detection angle
  ```

---

## Credits

- **Brody:** Special thanks for the contributions to the NCTR.lua mod.

---

**Disclaimer:** Use these mods at your own risk. Always backup your original files before making any modifications. These mods are not endorsed by Eagle Dynamics or Razbam.

---
