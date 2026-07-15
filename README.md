[🇷🇺 Читать на русском](README-RU.md)

# Unity Toolbox

A collection of Unity Editor tools designed to speed up common development workflows and eliminate repetitive tasks. All scripts are located inside the `Editor/` folder and are available from the following menus:

- `Tools/Megxlord Toolbox`
- `Tools/Megxlord uGUI`

---

# Contents

- [2D](#2d)
- [3D](#3d)
- [Editor Settings](#editor-settings)
- [Hierarchy](#hierarchy)
- [Marketing](#marketing)
- [PlayMode](#playmode)
- [Scripts](#scripts)
- [uGUI](#ugui)
- [Installation](#installation)
- [Requirements](#requirements)

---

# 2D

Folder: `Editor/2D/`

## ObjectSnap.cs

**Menu:** `Tools/Megxlord Toolbox/2D/Object Snap 2D`

Aligns all selected 2D objects to the position of the primary selection (the last selected object). The primary object remains in place while all other selected objects are moved to its X and Y coordinates.

**Purpose:** Quickly align sprites without manually copying coordinates. Supports Undo.

---

## Scale Calculator 2D.cs

**Menu:** `Tools/Megxlord Toolbox/2D/Scale Calculator 2D`

An advanced scaling calculator for 2D sprites. Automatically detects the `SpriteRenderer` draw mode (`Simple`, `Sliced`, or `Tiled`) and applies the appropriate resizing method.

### Features

- Aspect ratio presets (1:1, 4:3, 16:9, 9:16, etc.)
- Scaling modes:
  - Longest Side
  - Shortest Side
  - Width
  - Height
- Keep Aspect Ratio
- Auto-apply to selected objects
- Integer rounding
- Copy/Paste dimensions
- Restore original values

**Purpose:** Precisely resize sprites while preserving proportions. Useful for preparing assets for UI and 2D games.

---

## Sprite2DOrderManager.cs

**Menu:** `Tools/Megxlord Toolbox/2D/Sprite2D Order Manager`

A scene-wide rendering order manager for 2D objects.

Supports:

- SpriteRenderer
- TextMeshPro
- MeshRenderer
- ParticleSystemRenderer
- TilemapRenderer
- SpriteMask
- LineRenderer
- TrailRenderer
- SkinnedMeshRenderer

### Features

- Renderer table with:
  - Enabled state
  - Component type
  - Object name
  - Sorting Layer
  - Order in Layer
  - Rendering Layer Mask
  - Color
- Filtering by renderer type, search, and sorting layer
- Batch editing of Sorting Layer, Order in Layer, and Color
- Detection of rendering conflicts (overlapping renderers sharing the same Order in Layer)
- Rendering order visualization
- Scene statistics
- Enable/disable GameObjects

**Purpose:** Efficiently organize rendering order for large 2D scenes and detect sorting conflicts.

---

# 3D

Folder: `Editor/3D/`

## RandomScale.cs

**Menu:** `Tools/Megxlord Toolbox/3D/RandomScale`

Applies a random scale within a configurable range to all selected objects.

Ideal for adding natural variation to rocks, trees, vegetation, and other environmental props.

**Purpose:** Quickly introduce visual variety without manually scaling every object.

---

## SnapToTerrain.cs

**Menu:** `Tools/Megxlord Toolbox/3D/Snap To Terrain`

Snaps selected objects to the terrain surface.

Supports two placement modes:

- **Edge Pivot** — the object's lowest point touches the terrain.
- **Center Pivot** — aligns the object's center while compensating for mesh bounds.

Supports both English and Russian localization.

**Purpose:** Automatically place props such as trees, rocks, buildings, and other objects onto terrain.

---

# Editor Settings

Folder: `Editor/Editor Settings/`

## FastObjects.cs

**Menu:**

- `FastObjects/Make Asmdef`
- `FastObjects/Make Asmdef Ref`

Quickly creates Assembly Definition (`.asmdef`) and Assembly Definition Reference (`.asmref`) assets.

**Purpose:** Simplifies project organization using Assembly Definitions.

---

## Hotkeys.cs

**Menu:** `HotKey/`

Adds shortcuts for frequently used editor operations.

| Shortcut | Action |
|----------|--------|
| `B` | Play + Refresh Assets |
| `Shift+B` | Toggle Play Mode |
| `F5` | Refresh Assets |
| `F12` | Create Folder |
| `Shift+5` | Create Empty C# Script |
| `1` | Open Input System Settings |

**Purpose:** Reduce repetitive editor actions and speed up everyday workflow.

---

## SceneSwitcherToolbar.cs

Adds two dropdowns to Unity's main toolbar.

### Modes

1. All Scenes
2. Work Scenes
3. Scenes in Build

### Features

- Quick scene switching
- Build Settings filtering
- Runtime scene loading in Play Mode
- Automatic refresh when project assets change

**Purpose:** Instantly switch between scenes without searching in the Project window.

---

## SmartProjectMenu.cs

**Menu:** `Analyze/`

Provides quick access to Unity rendering analysis tools:

- Frame Debugger
- Render Graph Viewer
- Rendering Debugger

**Purpose:** One-click access to Unity's rendering diagnostics.

---

# Hierarchy

Folder: `Editor/Hierarchy/`

## MissingScriptValidator.cs

**Menu:** `Tools/Megxlord Toolbox/Hierarchy/Missing Script Validator`

Scans every GameObject in the current scene for missing script references.

Displays:

- Object name
- Hierarchy path
- Number of missing components
- Select button for quick navigation

**Purpose:** Detect broken script references after refactoring, importing assets, or upgrading projects.

---

## Polycount Viewer.cs

**Menu:** `Tools/Megxlord Toolbox/Hierarchy/Polycount Viewer`

Displays polygon and vertex statistics for selected objects.

### Features

- MeshFilter vertex count
- MeshCollider vertex count
- Total polycount for prefabs
- LODGroup statistics (including LOD0)

**Purpose:** Quickly identify high-polygon assets during optimization.

---

# Marketing

Folder: `Editor/Marketing/`

## PocketPublisherTool.cs

**Menu:** `Tools/Megxlord Toolbox/Marketing/Pocket Publisher Tool`

A utility for generating marketing assets.

### Screenshot

- Capture using `Camera.Render` or Game View
- Configurable resolution and aspect ratio
- Automatic camera detection
- PNG export

### GIF Recorder *(planned)*

- FPS
- Duration
- Loop settings

### Batch Mode

- Process multiple scenes
- Automatically generate screenshots and GIFs

**Purpose:** Quickly create screenshots and promotional assets for Steam, Google Play, and the App Store.

---

# PlayMode

Folder: `Editor/PlayMode/`

## TrueFullscreenGameView.cs

**Menu:** `Tools/Megxlord Toolbox/Fullscreen/Toggle Fullscreen GameView` (`F11`)

Provides a true fullscreen Game View using the Windows API instead of Unity's built-in maximized mode.

### Features

- Win32 API implementation
- `WS_POPUP` window style
- Borderless fullscreen
- Removes toolbar and window padding
- Exit with `Escape`
- Optional automatic fullscreen when entering Play Mode

**Purpose:** Test games in true fullscreen directly inside the Unity Editor.

> **Note:** Windows Editor only (`UNITY_EDITOR_WIN`).

---

# Scripts

Folder: `Editor/Scripts/`

## ReferencingScriptsWindow.cs

**Menu:** `Tools/Megxlord Toolbox/Scripts/Find Referencing Scripts`

Finds every script in the project that references the selected class.

Performs source code analysis while ignoring comments and string literals.

Detects:

- Inheritance
- Object instantiation
- Variable declarations
- Method calls

**Purpose:** Analyze dependencies before refactoring or removing a class.

---

## ScriptUsageFinder.cs

**Menu:** `Tools/Megxlord Toolbox/Scripts/Find Script Usage`

Searches the current scene and every prefab in the project for components of the selected script.

Supports drag-and-drop of `MonoScript` assets.

**Purpose:** Locate every GameObject using a specific component before modifying or deleting it.

---

## ScriptArchitecture.cs

**Menu:** `Tools/Megxlord Toolbox/Scripts/Script Architecture`

An advanced script performance analyzer.

Scans all C# files under `Assets/` and identifies methods executed every frame.

### Supported callbacks

- Update
- LateUpdate
- FixedUpdate
- OnGUI
- OnAnimatorMove
- OnAnimatorIK
- OnRenderObject
- OnWillRenderObject

Each method receives a **Load Score (0–100)** based on:

- Callback type
- Method size
- Performance risk patterns

### Risk Flags

| Flag | Description |
|------|-------------|
| `A` | Allocations (`new`, `Instantiate`, `GetComponent`) |
| `F` | Scene-wide searches (`FindObjectsOfType`, `GameObject.Find`) |
| `SM` | `SendMessage` / `BroadcastMessage` |
| `RC` | Physics queries (`Raycast`, `OverlapSphere`, etc.) |
| `LQ` | LINQ usage |
| `N²` | Nested loops |
| `LP` | Loops |
| `MC` | Additional method calls |

### Features

- Parallel scanning
- Filtering
- Sorting
- Optimization recommendations

**Purpose:** Identify potential performance bottlenecks before profiling.

---

# uGUI

Folder: `Editor/uGUI/`

## AnchorsToCornersChecker.cs

**Menu:** `Tools/Megxlord uGUI/Anchors to Corners Checker`

Validates `RectTransform`s using Stretch anchors.

Checks that:

- `anchorMin` / `anchorMax` match the visual bounds
- Offsets are zero

Options:

- Ignore Text and TMP components
- Validate fixed anchors
- Include inactive objects

**Purpose:** Detect incorrectly configured UI anchors.

---

## AnchorsToCornersEditor.cs

**Menu:** `Tools/Megxlord uGUI/Anchors to Corners`

Automatically adjusts anchors to match the current visual bounds of selected `RectTransform`s and resets offsets to zero.

Supports multi-selection.

**Purpose:** Convert existing UI layouts into properly configured anchors with a single click.

---

## Scale Calculator.cs

**Menu:** `Tools/Megxlord uGUI/Scale Calculator`

A comprehensive UI scaling utility with four tabs.

### Scale Calculator

- Free Scale
- Scale by Width
- Scale by Height
- Fit Inside
- Fill Outside
- Uniform Scale slider
- ×2 / ×½ / ×3 shortcuts
- Apply size or scale to selected `RectTransform`s

### Ratio Calculator

- Calculate missing dimensions
- Aspect ratio visualization
- Common aspect ratios

### Resolution Calculator

- Convert between common device resolutions
- UI scaling reference table

### Batch Scale

- Scale multiple objects
- `localScale` or `sizeDelta`
- Preserve world position
- Preview changes

**Purpose:** Resize and adapt UI for different screen resolutions.

---

## Simple2DPivotEditor.cs

**Menu:** `Tools/Megxlord uGUI/Simple2DPivotEditor`

Interactive pivot editor for `RectTransform`s.

### Features

- Drag-and-drop pivot editing
- Nine preset positions
- Grid snapping
- Live preview
- Preserve world position
- Multi-selection
- Optional child anchor adjustment

Adds a **Pivot** button to Unity's main toolbar.

**Purpose:** Simplify pivot editing for UI animation and layout workflows.

---

## UIRectValidatorWindow.cs

**Menu:** `Tools/Megxlord uGUI/UI Rect Validator`

Validates `RectTransform` values throughout the scene.

Checks:

- Anchored Position
- Offsets
- SizeDelta
- Width / Height
- Scale (should be `1,1,1`)
- Rotation (should be `0,0,0`)

Reports:

- Fractional values
- Odd integer values

**Purpose:** Detect UI values that may cause blurry rendering or inconsistent layouts across different resolutions.

---

## FigmaLayoutEditor.cs

**Menu:** `Tools/Megxlord uGUI/Figma Layout Editor`

A visual UI layout editor inspired by Figma constraints.

Allows editing margins (`Left`, `Right`, `Top`, `Bottom`) and dimensions relative to the parent `RectTransform`.

### Tabs

- Layout
- Align
- Constraints
- Settings

### Features

- Parent or Canvas reference mode
- Zoom and Pan
- Grid and rulers
- Live Scene View overlay
- Pixel snapping
- Grid snapping
- Safe area visualization
- Interactive resize handles

**Purpose:** Position UI using margins and constraints instead of manually editing anchors and `anchoredPosition`, providing a workflow similar to Figma.

---

# Installation

1. Copy the `Editor/` folder into your Unity project's `Assets/` directory.
2. Ensure that `MyEditorScripts.asmdef` is included.
3. All tools will appear under:
   - `Tools/Megxlord Toolbox`
   - `Tools/Megxlord uGUI`

---

# Requirements

- Unity 2021.3 or newer
- Some features rely on `FindObjectsByType`, available in Unity 6.
- TextMeshPro (optional; required only for TMP support in `Sprite2DOrderManager`).