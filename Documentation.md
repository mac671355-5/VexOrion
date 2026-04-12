# 🌌 Orion Library Documentation

Orion is a modern, high-performance UI library for Roblox with integrated Lucide icons, a robust configuration system, and a flexible theme engine.

---

## 🚀 Getting Started

To use the library, load it into your script:

```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/mac671355-5/VexOrion/refs/heads/main/Orion.lua"))() 

```

## 🪟 Creating a Window

The window is the main container for your UI.

```lua
local Window = Library:MakeWindow({
    Name = "My Script",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionProject",
    IntroEnabled = true,
    Theme = "WinUI", -- Choose from available themes
    ShowIcon = true,
    Icon = "home"
})
```

### 🎨 Theme System
Orion now supports dynamic themes. You can set them at startup or change them live.

**Available Themes:**
- `Default`: The classic Orion look.
- `Dark`: A deep dark mode with grey accents.
- `Light`: A clean, readable light mode.
- `WinUI`: A modern, Windows 11-inspired grey layout.
- `Grape`: Purple-themed accents.
- `Ocean`: Blue-themed accents.
- `Rose`: Pink-themed accents.

**Change Theme Live:**
```lua
Library:SetTheme("Rose")
```

**Custom Themes:**
You can also pass a custom table to `SetTheme`:
```lua
Library:SetTheme({
    Main = Color3.fromRGB(20, 20, 20),
    Second = Color3.fromRGB(30, 30, 30),
    Stroke = Color3.fromRGB(255, 0, 0),
    Divider = Color3.fromRGB(40, 40, 40),
    Text = Color3.fromRGB(255, 255, 255),
    TextDark = Color3.fromRGB(150, 150, 150)
})
```

---

## 📑 Tabs and Sections

```lua
local Tab = Window:MakeTab({
    Name = "Home",
    Icon = "home"
})

local Section = Tab:AddSection({
    Name = "Main Features"
})
```

---

## 🧱 UI Elements

| Element | Description |
| :--- | :--- |
| `AddToggle` | Toggle with automatic saving. |
| `AddSlider` | Numeric slider with real-time saving. |
| `AddButton` | Clickable action button. |
| `AddDropdown` | Single or Multi-select dropdown menu. |
| `AddColorpicker` | Professional color choice tool. |
| `AddBind` | Assign functions to keyboard keys. |
| `AddTextbox` | Inline text input. |

---

## 💾 Configuration System

Orion comes with a built-in manager (access via the slider icon in the top right).

### Features
1. **Selection**: Switch between multiple config files.
2. **Autoload**: Set a profile to load automatically whenever the script starts.
3. **Save/New**: Create custom profiles for different scenarios.

---

## 📱 Mobile Support

The library automatically detects mobile players and:
- Resizes the window to `480x270`.
- Optimizes button sizes for touch screens.
- Centers the UI on the smaller display area.
