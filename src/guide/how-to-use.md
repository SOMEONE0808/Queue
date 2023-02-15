# How to use
```lua
local QueueModule = require(game.ReplicatedStorage.Modules.Queue)
local Queue = QueueModule.new("Queue", true)

local function F(...)
    print(...)
    task.wait(1)
end


Queue:Wait(1)
for i = 1, 5 do
    Queue:Add({1, 2, 3}, F)
end
```