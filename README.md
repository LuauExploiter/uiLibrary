```markdown
Hiklo's UI Library

A clean Roblox UI library with a notification system.

## Installation


local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()
```

Usage

Create Window

```lua
local UI = UILibrary:Create("Window Title")
```

Create Tab

```lua
local Tab = UI:Tab("Tab Name")
```

Add Button

```lua
Tab:AddButton("Button Text", function()
    print("Button clicked")
end)
```

Add Toggle

```lua
Tab:AddToggle("Toggle Text", false, function(state)
    print("Toggle:", state)
end)
```

Add Dropdown

```lua
Tab:AddDropdown("Dropdown Text", {"Option 1", "Option 2", "Option 3"}, function(selected)
    print("Selected:", selected)
end)
```

Show Notification

```lua
UI:Notify("Title", "Message", "Type", duration)
```

Types: "Success", "Warning", "Error", "Info"
Duration: seconds (optional, default: 5)

Example

```lua
local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()

local window = UILibrary:Create("My Script")
local main = window:Tab("Main")

main:AddButton("Test", function()
    window:Notify("Button", "Clicked!", "Success", 3)
end)

main:AddDropdown("Options", {"A", "B", "C"}, function(selected)
    window:Notify("Selected", selected, "Info", 2)
end)
```

Features

· Draggable window
· Tab system
· Notification system (middle-right)
· Smooth animations
· Auto-closing notifications
· Fixed dropdowns

```
```
