# 🌌 Orion Library - Ultimate Documentation (WinUI 2.0)

Orion is a state-of-the-art UI library for Roblox, redesigned from the ground up to follow modern design principles, including **WinUI aesthetics**, **Glassmorphism**, and a unified **Premium Dark Mode**.

---

## 🚀 Getting Started

### 📦 Initialization
First, load the library into your script.
```lua
local OrionLib = loadstring(readfile("Orion.lua"))()
```

### 🪟 Creating a Window
The window acts as the main container for your tabs and elements.
```lua
local Window = OrionLib:MakeWindow({
    Name = "Orion v2.0 | Dark Mode",
    ShowIcon = true,
    Icon = "shield-check", -- Use any Lucide icon name
    Transparent = true,    -- Glassmorphism effect
    SidebarWidth = 200,    -- Customize the left sidebar width
    IntroEnabled = true,   -- Cool startup animation
    IntroText = "Initializing System",
    ConfigFolder = "OrionSettings", -- Folder for saving configs
    SaveConfig = true      -- Enable the config system
})
```

---

## 📑 Tabs & Organization

### 🗂️ Adding a Tab
Tabs allow you to categorize your script features.
```lua
local Tab = Window:MakeTab({
    Name = "Visuals",
    Icon = "eye", -- Use any Lucide icon name
    PremiumOnly = false -- If true, locks the tab for non-sirius premium users
})
```

### 🧱 Adding a Section
Sections help group elements within a tab.
```lua
local Section = Tab:AddSection({
    Name = "Player Enhancements"
})
```

---

## 🕹️ Interactive Elements

### 🔘 Buttons
Simple action triggers with hover & click animations.
```lua
Tab:AddButton({
    Name = "Destroy All Humans",
    Icon = "zap",
    Callback = function()
        print("Button clicked!")
    end
})
```

### 🏁 Checkboxes (Toggles)
Modern square WinUI checkboxes for boolean settings.
```lua
Tab:AddCheckbox({
    Name = "Enable Godmode",
    Default = false,
    Callback = function(Value)
        print("Godmode:", Value)
    end
})
```

### 🎚️ Sliders
Precise sliders for numerical values.
```lua
Tab:AddSlider({
    Name = "Walkspeed Offset",
    Min = 0,
    Max = 100,
    Default = 16,
    ValueName = "pps", -- Postfix for the value label
    Callback = function(Value)
        print("Speed:", Value)
    end
})
```

### ⌨️ Keybinds
Customizable key triggers for your functions.
```lua
Tab:AddKeybind({
    Name = "Kill-Switch",
    Default = Enum.KeyCode.F,
    Hold = false, -- If true, triggers while holding
    Callback = function()
        print("Keybind triggered!")
    end
})
```

### 📝 Textboxes (Inputs)
Allows users to enter custom text or values.
```lua
Tab:AddTextbox({
    Name = "Custom Message",
    Default = "",
    TextDisappear = true, -- Clears after Enter is pressed
    Callback = function(Value)
        print("User entered:", Value)
    end
})
```

### 🔽 Dropdowns
Selection menus for multiple options.
```lua
Tab:AddDropdown({
    Name = "Choose Weapon",
    Default = "Sword",
    Options = {"Sword", "Axe", "Bow"},
    Callback = function(Value)
        print("Selected:", Value)
    end
})
```

### 🎨 Colorpickers
Full RGB/HSV color selection menu.
```lua
Tab:AddColorpicker({
    Name = "UI Accent",
    Default = Color3.fromRGB(120, 140, 255),
    Callback = function(Value)
        print("Selected Color:", Value)
    end
})
```

---

## 📢 Notifications & Dialogues

### 🔔 Notifications
Temporary toast messages at the bottom-right corner.
```lua
OrionLib:MakeNotification({
    Name = "Success",
    Content = "The exploit has been injected!",
    Image = "check-circle",
    Time = 5
})
```

### 💬 Dialogues
Modal popups that require user interaction.
```lua
OrionLib:MakeDialog({
    Title = "Confirm Action",
    Content = "Do you really want to reset your character?",
    Buttons = {
        {
            Name = "Confirm",
            Callback = function() print("Confirmed!") end
        },
        {
            Name = "Cancel",
            Callback = function() print("Cancelled.") end
        }
    }
})
```

---

## 🛠️ Advanced Features

### 🏘️ Paragraphs
Informational text blocks with icons.
```lua
Tab:AddParagraph({
    Title = "Warning",
    Content = "Using this feature may result in a ban.",
    Icon = "alert-triangle"
})
```

### 📂 Config System
Orion handles configuration saving automatically if `SaveConfig` is enabled. A hidden **"Configs"** tab appears in the library where users can Save, Load, and Delete presets.

### 🖼️ Image Labels
```lua
Tab:AddImage({
    Icon = "user", -- Lucide or Asset ID
    Size = UDim2.new(0, 50, 0, 50)
})
```

### 🏁 Initializing
Must be called at the end of your script to finalize the UI.
```lua
OrionLib:Init()
```
