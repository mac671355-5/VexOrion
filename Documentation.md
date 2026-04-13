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
    Resizable = true, -- Enable manual resizing
    BackgroundImage = "rbxassetid://..." -- Add a background image
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

### 🔽 Dropdowns
```lua
Tab:AddDropdown({
	Name = "Select Option",
	Default = "1",
	Options = {"1", "2", "3"},
	MultiSelect = false,
	Callback = function(Value)
		print(Value)
	end    
})
```

### 🎨 Color Picker
```lua
Tab:AddColorpicker({
	Name = "Theme Color",
	Default = Color3.fromRGB(255, 0, 0),
	Callback = function(Value)
		print(Value)
	end	  
})
```

### ⌨️ Keybinds
```lua
Tab:AddBind({
	Name = "Kill Bind",
	Default = Enum.KeyCode.E,
	Hold = false,
	Callback = function()
		print("Power activated!")
	end    
})
```

### 📝 Textboxes
```lua
Tab:AddTextbox({
	Name = "Input",
	Default = "Default value",
	TextDisappear = true,
	Callback = function(Value)
		print(Value)
	end	  
})
```

---

## ✨ New Layout Elements

### 📏 Dividers & Spacers
Organize your elements with clean lines and spacing.
```lua
Tab:AddDivider()
Tab:AddSpacer(20) -- Adds 20 pixels of empty space
```

### 💻 Code Blocks
Display code or logs with a copy-to-clipboard button.
```lua
Tab:AddCode("print('The code is here!')")
```

---

## 💬 Feedback & Modals

### 🔔 Notifications
```lua
OrionLib:MakeNotification({
	Name = "System",
	Content = "Action completed successfully!",
	Image = "check",
	Time = 5
})
```

### 💬 Dialogs (Modals)
Dialogs require user interaction and block the background.
```lua
OrionLib:MakeDialog({
    Title = "Warning",
    Content = "This will delete all data. Proceed?",
    Buttons = {
        {
            Name = "Yes",
            Callback = function() print("Deleted") end
        },
        {
            Name = "No",
            Callback = function() print("Aborted") end
        }
    }
})
```

---

## 💾 Saving & Configurations
To save settings, add `Flag` and `Save` to any compatible element (Toggle, Slider, Dropdown, Bind, Colorpicker).

```lua
Tab:AddToggle({
    Name = "Auto-Farm",
    Default = false,
    Flag = "AutoFarm",
    Save = true
})

-- Access value anywhere:
local val = OrionLib.Flags["AutoFarm"].Value
```

---

# 🏁 Finalizing (REQUIRED)
The below function must be called at the very end of your script.
```lua
OrionLib:Init()
```

### 🧹 Cleanup
```lua
OrionLib:Destroy()
```
