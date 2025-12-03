```markdown
Hiklo's UI Library

A lightweight Roblox Lua UI library with notifications.

## Installation

local uilib = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()
```

Basic Usage

Create Window

```lua
local ui = uilib:create("Window Title")
```

Create Tab

```lua
local tab = ui:tab("Tab Name")
```

Add Button

```lua
tab:addbutton("Button", function()
    print("Clicked")
end)
```

Add Toggle

```lua
tab:addtoggle("Toggle", false, function(state)
    print(state)
end)
```

Add Dropdown

```lua
tab:adddropdown("Dropdown", {"1","2","3"}, function(selected)
    print(selected)
end)
```

Show Notification

```lua
ui:notify("Title", "Message", "Type", 5)
```

Types: "success", "warning", "error", "info"

Example

```lua
local uilib = loadstring(game:HttpGet("https://raw.githubusercontent.com/LuauExploiter/uiLibrary/refs/heads/main/Library"))()

local window = uilib:create("My UI")
local main = window:tab("Main")

main:addbutton("Test", function()
    window:notify("Test", "Button clicked", "success", 3)
end)

main:adddropdown("Options", {"A","B","C"}, function(opt)
    window:notify("Selected", opt, "info", 2)
end)
```
