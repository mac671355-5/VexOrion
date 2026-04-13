# 🌌 Orion Library - Premium Documentation

Orion is a powerful, modern UI library for Roblox, enhanced with WindUI-inspired features. It offers high performance, Lucide icons, a flexible theme engine, and a robust configuration system.

---

## 🚀 Getting Started

To use the library, load it into your script:

```lua
local OrionLib = loadstring(readfile("Orion.lua"))()
```

---

## 🪟 Creating a Window
The window is the core container for your interface.

```lua
local Window = OrionLib:MakeWindow({
    Name = "My Script",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionProject",
    IntroEnabled = true,
    Theme = "WinUI", -- WinUI, Dark, Light, Grape, Ocean, Rose, Default
    Transparent = true, -- Adds a modern glass effect
    SidebarWidth = 180, -- Customize your sidebar width
    Resizable = true -- Enable manual resizing
})
```

---

## 🎨 Theme System
Orion supports dynamic themes. You can set them at startup or change them live.

**Change Theme Live:**
```lua
OrionLib:SetTheme("Rose")
```

---

## 📑 Creating a Tab
Tabs allow you to organize your features.

```lua
local Tab = Window:MakeTab({
	Name = "Home",
	Icon = "home",
	Color = Color3.fromRGB(161, 133, 255), -- Set a custom accent color for this tab
	PremiumOnly = false
})
```

---

## 🧱 UI Elements

### 🏠 Labels & Paragraphs
```lua
Tab:AddLabel("Simple Label")
Tab:AddParagraph("Title", "Content text goes here...")
```

### 🔘 Buttons
```lua
Tab:AddButton({
	Name = "Press Me!",
	Callback = function()
		print("Button clicked")
	end    
})
```

### 🔘 Toggles
```lua
Tab:AddToggle({
	Name = "Enabled",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})
```

### 🎚️ Sliders
```lua
Tab:AddSlider({
	Name = "Sensitivity",
	Min = 0,
	Max = 100,
	Default = 50,
	Increment = 1,
	ValueName = "units",
	Callback = function(Value)
		print(Value)
	end    
})
```

---

## ✨ Layout Elements

### 📏 Dividers & Spacers
```lua
Tab:AddDivider()
Tab:AddSpacer(20)
```

### 💻 Code Blocks
Display code with a copy button.
```lua
Tab:AddCode("print('Hello World')")
```

---

## 💬 Feedback & System

### 🔔 Notifications
```lua
OrionLib:MakeNotification({
	Name = "System",
	Content = "Ready!",
	Image = "check",
	Time = 5
})
```

### 💬 Dialogs (Modals)
```lua
OrionLib:MakeDialog({
    Title = "Warning",
    Content = "Discard changes?",
    Buttons = {
        { Name = "Yes", Callback = function() end },
        { Name = "No", Callback = function() end }
    }
})
```

---

# 🏁 Finalizing (REQUIRED)
```lua
OrionLib:Init()
```
