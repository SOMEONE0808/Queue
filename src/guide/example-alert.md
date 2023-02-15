# Example: Alert
UI) ScreenGui -> (LocalScript, TextLabel)
```lua
local TweenService = game:GetService("TweenService")
local tweenInfo = TweenInfo.new(0.5)

local Queue = require(game.ReplicatedStorage.Modules.Queue)
local queue = Queue.new("text", true)

local Gui = script.Parent
local TextLabel = Gui:WaitForChild("TextLabel")

local pos = TextLabel.Position
local tween = TweenService:Create(
    TextLabel, tweenInfo, {Position = pos - UDim2.fromScale(0, 0.05),
        TextTransparency = 1})

local function F(id, text)
    TextLabel.Position = pos
    TextLabel.Text = id
    TextLabel.TextTransparency = 0
    task.wait(1)
    tween:Play()
    tween.Completed:Wait()
end

queue:Wait(3)
for i = 1, 5 do
    task.spawn(function()
        queue:Add({1, 2, 3}, F)
    end)
end
```