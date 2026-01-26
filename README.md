Hiklo's UI Library

A modern, customizable Roblox UI library with complete components and optional icon support.

Installation

```lua
local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()
```

Basic Usage

Create Window

```lua
local UI = UILibrary:Create("Window Title")
```

Create Tab with Optional Icon

```lua
-- Tab without icon
local Tab1 = UI:Tab("Main")

-- Tab with icon (optional)
local Tab2 = UI:Tab("Settings", "rbxassetid://6031307514")
```

Components with Optional Icons

All components support an optional icon parameter as the last argument. Icons are completely optional!

Button

```lua
-- Button without icon
Tab:AddButton("Click Me", function()
    print("Clicked!")
end)

-- Button with icon (optional)
Tab:AddButton("Execute", function()
    print("Executed!")
end, "rbxassetid://6031280882")
```

Toggle

```lua
-- Toggle without icon
local toggle = Tab:AddToggle("Enable Feature", false, function(state)
    print("State:", state)
end)

-- Toggle with icon (optional)
local toggle2 = Tab:AddToggle("God Mode", false, function(state)
    print("God Mode:", state)
end, "rbxassetid://6031307514")

-- Methods
toggle:Set(true)
print(toggle:Get())
```

Dropdown

```lua
-- Dropdown without icon
local dropdown = Tab:AddDropdown("Options", {"A", "B", "C"}, function(selected)
    print("Selected:", selected)
end)

-- Dropdown with icon (optional)
local dropdown2 = Tab:AddDropdown("Weapons", {"Sword", "Gun", "Bow"}, function(selected)
    print("Selected weapon:", selected)
end, "rbxassetid://6031307548")

-- Methods
dropdown:Set("A")
print(dropdown:Get())
```

Textbox

```lua
-- Textbox without icon
local textbox = Tab:AddTextbox("Username", "Enter name...", function(text)
    print("Input:", text)
end)

-- Textbox with icon (optional)
local textbox2 = Tab:AddTextbox("Password", "Enter password...", function(text)
    print("Password:", text)
end, "rbxassetid://6031307549")

-- Methods
textbox:Set("Player1")
print(textbox:Get())
```

Slider

```lua
-- Slider without icon
local slider = Tab:AddSlider("Volume", 0, 100, 50, function(value)
    print("Volume:", value)
end)

-- Slider with icon (optional)
local slider2 = Tab:AddSlider("Walk Speed", 16, 100, 16, function(value)
    print("Walk Speed:", value)
end, "rbxassetid://6031307539")

-- Methods
slider:Set(75)
print(slider:Get())
```

Label

```lua
-- Label without icon
Tab:AddLabel("Welcome!")

-- Label with icon (optional)
Tab:AddLabel("Settings", "rbxassetid://6031307514")
```

Keybind

```lua
-- Keybind without icon
local keybind = Tab:AddKeybind("Toggle UI", Enum.KeyCode.RightShift, function(key, pressed)
    print("Key:", key.Name, "Pressed:", pressed)
end)

-- Keybind with icon (optional)
local keybind2 = Tab:AddKeybind("Fly", Enum.KeyCode.F, function(key, pressed)
    print("Fly key:", key.Name)
end, "rbxassetid://6031307537")

-- Methods
keybind:Set(Enum.KeyCode.F)
print(keybind:Get())
```

Colorpicker

```lua
-- Colorpicker without icon
local colorpicker = Tab:AddColorpicker("UI Color", Color3.fromRGB(0, 120, 255), function(color)
    print("Color:", color)
end)

-- Colorpicker with icon (optional)
local colorpicker2 = Tab:AddColorpicker("Theme", Color3.new(1, 0, 0), function(color)
    print("Theme color:", color)
end, "rbxassetid://6031307544")

-- Methods
colorpicker:Set(Color3.new(0, 1, 0))
print(colorpicker:Get())
```

Notifications

```lua
-- Create notification
UI:Notify("Success", "Operation completed!", "Success", 5)
Tab:Notify("Warning", "Be careful!", "Warning", 3)

-- Notification types: "Success", "Warning", "Error", "Info"
```

Full Example

```lua
local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()

local UI = UILibrary:Create("My UI")

-- Tab with icon
local Main = UI:Tab("Main", "rbxassetid://6031075938")

-- Button with icon
Main:AddButton("Execute", function()
    UI:Notify("Success", "Script executed!", "Success", 3)
end, "rbxassetid://6031280882")

-- Toggle without icon
local toggle = Main:AddToggle("God Mode", false, function(state)
    UI:Notify("Info", state and "Enabled" or "Disabled", "Info", 2)
end)

-- Dropdown with icon
local dropdown = Main:AddDropdown("Weapons", {"Sword", "Gun", "Bow"}, function(selected)
    UI:Notify("Selected", "You chose: " .. selected, "Info", 2)
end, "rbxassetid://6031307548")

-- Settings tab without icon
local Settings = UI:Tab("Settings")

-- Slider with icon
local slider = Settings:AddSlider("Volume", 0, 100, 50, function(value)
    print("Volume set to:", value)
end, "rbxassetid://6031307539")

-- Label with icon
Settings:AddLabel("Appearance", "rbxassetid://6031307514")

-- Textbox without icon
local textbox = Settings:AddTextbox("Username", "Enter name...", function(text)
    print("Username:", text)
end)

-- Show welcome notification
UI:Notify("Welcome", "UI loaded successfully!", "Success", 4)
```

Features

· ✅ Modern dark theme
· ✅ Smooth animations
· ✅ Drag & drop window
· ✅ Minimize/close buttons
· ✅ Optional icon support for all components
· ✅ Responsive notifications
· ✅ Tabbed interface
· ✅ Auto-scrolling content
· ✅ Mobile friendly
· ✅ Backward compatible

Icon Requirements

· Icons are completely optional
· Use Roblox asset IDs: "rbxassetid://123456789"
· Recommended size: 20x20 pixels
· PNG format works best
· Transparent backgrounds recommended

Backward Compatibility

The library maintains 100% backward compatibility. All original functions work exactly as before. Icons are an optional addition that can be completely ignored.

```lua
-- This still works exactly as in the original version
Tab:AddButton("Click Me", function()
    print("Works without icons!")
end)
```

Notes

· Icons are positioned next to text
· Layout adjusts automatically when icons are present/absent
· All components work with or without icons
· Tab icons replace the tab text when provided
· Component icons appear next to labels

Example Icons (Roblox Asset IDs)

· Home: 6031075938
· Check: 6031302931
· Play: 6031280882
· Info: 6031307514
· Shield: 6031307514
· Speed: 6031307539
· Sword: 6031307548
· Settings: 6031307514
· Teleport: 6031307545
· Error: 6031307552
· Bird: 6031307537
· Paint: 6031307544

---

Made with ❤️ by Hiklo
