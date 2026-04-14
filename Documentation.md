# Orion UI Library Documentation

Orion is a powerful and modern UI library for Roblox, designed to be easy to use and highly customizable.

## 🚀 Getting Started

To use the library, you first need to load it and initialize your window.

```lua
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local Window = OrionLib:MakeWindow({
    Name = "Orion UI Library", 
    HidePremium = false, 
    SaveConfig = true, 
    ConfigFolder = "OrionTest",
    IntroEnabled = true,
    IntroText = "Welcome to Orion",
    IntroIcon = "rbxassetid://4483345998",
    Icon = "home",
    ShowIcon = true,
    Theme = "Dark"
})
```

---

## 🎨 Themes

Orion comes with several built-in themes:
- `Default`
- `Dark`
- `Light`
- `Grape`
- `Ocean`
- `Rose`
- `WinUI`

You can set the theme when creating the window or change it dynamically:
```lua
OrionLib:SetTheme("Grape")
```

---

## 📑 Tabs and Sections

Tabs are the main containers for your UI elements. Sections help organize elements within a tab.

```lua
local Tab = Window:MakeTab({
	Name = "Main Tab",
	Icon = "home",
	PremiumOnly = false
})

local Section = Tab:AddSection({
	Name = "Features"
})
```

---

## 🔘 Elements

### Label
Displays a simple line of text.
```lua
local Label = Tab:AddLabel("This is a label")
Label:Set("Updated Label Text")
```

### Paragraph
Displays a title and a longer block of text with an optional icon.
```lua
local Para = Tab:AddParagraph("Warning", "This is a serious warning!")
Para:Set("New Title", "New Content")
```

### Button
A clickable button with a callback.
```lua
Tab:AddButton({
	Name = "Click Me!",
	Callback = function()
		print("Button clicked!")
	end
})
```

### Toggle
A switch that can be on or off.
```lua
Tab:AddToggle({
	Name = "God Mode",
	Default = false,
	Callback = function(Value)
		print("God Mode:", Value)
	end    
})
```

### Slider
A slider for selecting numeric values.
```lua
Tab:AddSlider({
	Name = "WalkSpeed",
	Min = 16,
	Max = 100,
	Default = 16,
	Color = Color3.fromRGB(255,255,255),
	Increment = 1,
	ValueName = "Speed",
	Callback = function(Value)
		print(Value)
	end    
})
```

### Dropdown
A menu for selecting from multiple options.
```lua
local Dropdown = Tab:AddDropdown({
	Name = "Select Team",
	Default = "Neutral",
	Options = {"Team A", "Team B", "Neutral"},
	Callback = function(Value)
		print(Value)
	end    
})

-- Update options
Dropdown:Refresh({"New Option 1", "New Option 2"}, true)
```

### Colorpicker
Select a color.
```lua
Tab:AddColorpicker({
	Name = "UI Color",
	Default = Color3.fromRGB(255, 0, 0),
	Callback = function(Value)
		print(Value)
	end	  
})
```

### Textbox
An input field for user string input.
```lua
Tab:AddTextbox({
	Name = "Username",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		print(Value)
	end	  
})
```

### Keybind
A keybind system with support for holding.
```lua
Tab:AddBind({
	Name = "Kill All",
	Default = Enum.KeyCode.K,
	Hold = false,
	Callback = function()
		print("Bound key pressed!")
	end    
})
```

### Code Block
Displays formatted code with a copy button.
```lua
Tab:AddCode("print('Hello Orion!')")
```

---

## 🔔 Utilities

### Notifications
Send a notification to the user.
```lua
OrionLib:MakeNotification({
	Name = "Alert",
	Content = "Something happened!",
	Image = "rbxassetid://4483345998",
	Time = 5
})
```

### Dialogs
Show a confirmation dialog.
```lua
OrionLib:MakeDialog({
	Name = "Confirm",
	Content = "Do you want to continue?",
	Buttons = {
		{
			Name = "Yes",
			Callback = function()
				print("Confirmed!")
			end
		},
		{
			Name = "No",
			Callback = function()
				print("Cancelled!")
			end
		}
	}
})
```

### Cleanup
To properly initialize the library (autoloading configs):
```lua
OrionLib:Init()
```

To destroy the UI:
```lua
OrionLib:Destroy()
```
