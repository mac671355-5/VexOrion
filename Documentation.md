# 🌌 Modern Orion UI Library

A premium, modernized version of the Orion UI library featuring a sleek **Better EH** purple theme, dynamic **Lucide icons**, and a built-in **Config System**.

## 🚀 Quick Start

```lua
local OrionLib = loadstring(game:HttpGet("YOUR_LINK_HERE"))()

local Window = OrionLib:MakeWindow({
    Name = "Better EH",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionTest",
    Icon = "car-front", -- Lucide icon name
    ShowIcon = true
})

-- The window is automatically themed and includes a Config button in the top bar!
```

---

## 📑 Tabs & Sections

Tabs are the main containers for your elements. You can add sections within tabs to organize them.

### Create a Tab
```lua
local Tab = Window:MakeTab({
	Name = "Main",
	Icon = "home",
	PremiumOnly = false
})
```

### Create a Section
```lua
local Section = Tab:AddSection({
	Name = "Vehicle Settings"
})
```

---

## 🔘 UI Elements

### Button
Execute simple actions.
```lua
Tab:AddButton({
	Name = "Button!",
	Callback = function()
      		print("Clicked!")
  	end    
})
```

### Toggle (Checkbox)
Boolean switch for settings.
```lua
Tab:AddToggle({
	Name = "This is a toggle",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})
```

### Slider
Select numerical values with a custom increment.
```lua
Tab:AddSlider({
	Name = "Walkspeed",
	Min = 16,
	Max = 500,
	Default = 16,
	Color = Color3.fromRGB(161, 133, 255),
	Increment = 1,
	ValueName = "Speed",
	Callback = function(Value)
		print(Value)
	end    
})
```

### Dropdown (MultiSelect Support)
Select one or multiple options from a list.
```lua
Tab:AddDropdown({
	Name = "Dropdown",
	Default = "Option 1",
	Options = {"Option 1", "Option 2", "Option 3"},
	MultiSelect = true, -- Enable multiple selection
	Callback = function(Value)
		print(Value) -- Returns a table if MultiSelect is true
	end    
})
```

### Colorpicker
Choose a custom color.
```lua
Tab:AddColorpicker({
	Name = "UI Color",
	Default = Color3.fromRGB(255, 0, 0),
	Callback = function(Value)
		print(Value)
	end	  
})
```

### Keybind
Bind functions to a key or mouse button.
```lua
Tab:AddBind({
	Name = "Bind",
	Default = Enum.KeyCode.E,
	Hold = false,
	Callback = function()
		print("Bound Key Pressed")
	end    
})
```

### Textbox
Input custom text or commands.
```lua
Tab:AddTextbox({
	Name = "Textbox",
	Default = "default box",
	TextDisappear = true,
	Callback = function(Value)
		print(Value)
	end	  
})
```

---

## 🛠 Features

### 📁 Config System
The top-left button (icon: `file-sliders`) automatically opens the **Configs** tab. This allows users to save and load their settings easily without you having to code it!

### 🔔 Notifications
Show pop-up messages to the user.
```lua
OrionLib:MakeNotification({
	Name = "Title",
	Content = "Notification Content",
	Image = "rbxassetid://4483345998",
	Time = 5
})
```

### 🎨 Lucide Icon Support
Instead of `rbxassetid`, you can now use any icon name from [lucide.dev](https://lucide.dev/icons/).
Example: `Icon = "settings"`, `Icon = "user"`, `Icon = "star"`.

### 🏁 Initialization
Required at the end of your script to start the processing.
```lua
OrionLib:Init()
```
