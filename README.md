```markdown
# Hiklo's UI Library

A modern Roblox UI library with complete components and notifications.

## Installation
```lua
local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()
```

Basic Usage

Create Window

```lua
local UI = UILibrary:Create("Window Title")
```

Create Tab

```lua
local Tab = UI:Tab("Tab Name")
```

Components

Button

```lua
Tab:AddButton("Text", function()
    print("Clicked")
end)
```

Toggle

```lua
local toggle = Tab:AddToggle("Toggle", false, function(state)
    print(state)
end)

toggle:Set(true)
toggle:Get()
```

Dropdown

```lua
local dropdown = Tab:AddDropdown("Dropdown", {"Option1","Option2","Option3"}, function(selected)
    print(selected)
end)

dropdown:Set("Option1")
dropdown:Get()
```

Textbox

```lua
local textbox = Tab:AddTextbox("Label", "Placeholder", function(text)
    print(text)
end)

textbox:Set("Text")
textbox:Get()
```

Slider

```lua
local slider = Tab:AddSlider("Slider", 0, 100, 50, function(value)
    print(value)
end)

slider:Set(75)
slider:Get()
```

Label

```lua
Tab:AddLabel("Label Text")
```

Keybind

```lua
local keybind = Tab:AddKeybind("Keybind", Enum.KeyCode.F, function(key, pressed)
    print(key, pressed)
end)

keybind:Set(Enum.KeyCode.E)
keybind:Get()
```

Colorpicker

```lua
local colorpicker = Tab:AddColorpicker("Color", Color3.new(1,0,0), function(color)
    print(color)
end)

colorpicker:Set(Color3.new(0,1,0))
colorpicker:Get()
```

Notifications

```lua
UI:Notify("Title", "Message", "Type", 5)
Tab:Notify("Title", "Message", "Type", 5)

-- Types: "Success", "Warning", "Error", "Info"
```

Full Example

```lua
local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()

local UI = UILibrary:Create("My UI")
local Main = UI:Tab("Main")

Main:AddButton("Test", function()
    UI:Notify("Button", "Clicked!", "Success", 3)
end)

local toggle = Main:AddToggle("Enable", false, function(state)
    UI:Notify("Toggle", state and "On" or "Off", "Info", 2)
end)

local dropdown = Main:AddDropdown("Options", {"A","B","C"}, function(opt)
    UI:Notify("Selected", opt, "Warning", 2)
end)

local textbox = Main:AddTextbox("Input", "Type here", function(text)
    print("Input:", text)
end)
```
