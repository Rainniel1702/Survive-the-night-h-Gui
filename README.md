--// Created by Unordinary //

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local ScrollingFrame = Instance.new("ScrollingFrame")
local RelicESP = Instance.new("TextButton")
local RelicAura = Instance.new("TextButton")
local InstantBuild = Instance.new("TextButton")
local PlayerESP = Instance.new("TextButton")
local TextLabel = Instance.new("TextLabel")

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

Frame.Parent = ScreenGui
Frame.Active = true
Frame.BackgroundColor3 = Color3.fromRGB(119, 124, 127)
Frame.BorderColor3 = Color3.fromRGB(226, 226, 226)
Frame.Position = UDim2.new(0.833333313, 0, 0.606741607, 0)
Frame.Selectable = true
Frame.Size = UDim2.new(0, 153, 0, 33)
Frame.Draggable = true

ScrollingFrame.Parent = Frame
ScrollingFrame.BackgroundColor3 = Color3.fromRGB(119, 124, 127)
ScrollingFrame.BackgroundTransparency = 0.400
ScrollingFrame.BorderColor3 = Color3.fromRGB(119, 124, 127)
ScrollingFrame.BorderSizePixel = 0
ScrollingFrame.ClipsDescendants = false
ScrollingFrame.Position = UDim2.new(-0.00247571361, 0, 0.996060431, 0)
ScrollingFrame.Selectable = false
ScrollingFrame.Size = UDim2.new(0, 153, 0, 171)

RelicESP.Name = "Relic ESP"
RelicESP.Parent = ScrollingFrame
RelicESP.BackgroundColor3 = Color3.fromRGB(187, 255, 253)
RelicESP.BorderColor3 = Color3.fromRGB(187, 255, 253)
RelicESP.Position = UDim2.new(0.0424405783, 0, 0.035481751, 0)
RelicESP.Selectable = false
RelicESP.Size = UDim2.new(0, 140, 0, 20)
RelicESP.Font = Enum.Font.SourceSans
RelicESP.Text = "Relic ESP"
RelicESP.TextColor3 = Color3.fromRGB(0, 0, 0)
RelicESP.TextSize = 14.000

RelicAura.Name = "Relic Aura"
RelicAura.Parent = ScrollingFrame
RelicAura.BackgroundColor3 = Color3.fromRGB(187, 255, 253)
RelicAura.BorderColor3 = Color3.fromRGB(187, 255, 253)
RelicAura.Position = UDim2.new(0.0424405783, 0, 0.202148423, 0)
RelicAura.Selectable = false
RelicAura.Size = UDim2.new(0, 140, 0, 20)
RelicAura.Font = Enum.Font.SourceSans
RelicAura.Text = "Relic Aura"
RelicAura.TextColor3 = Color3.fromRGB(0, 0, 0)
RelicAura.TextSize = 14.000

InstantBuild.Name = "Instant Build"
InstantBuild.Parent = ScrollingFrame
InstantBuild.BackgroundColor3 = Color3.fromRGB(187, 255, 253)
InstantBuild.BorderColor3 = Color3.fromRGB(187, 255, 253)
InstantBuild.Position = UDim2.new(0.0424405783, 0, 0.368815064, 0)
InstantBuild.Selectable = false
InstantBuild.Size = UDim2.new(0, 140, 0, 20)
InstantBuild.Font = Enum.Font.SourceSans
InstantBuild.Text = "Instant Build"
InstantBuild.TextColor3 = Color3.fromRGB(0, 0, 0)
InstantBuild.TextSize = 14.000

PlayerESP.Name = "Player ESP"
PlayerESP.Parent = ScrollingFrame
PlayerESP.BackgroundColor3 = Color3.fromRGB(187, 255, 253)
PlayerESP.BorderColor3 = Color3.fromRGB(187, 255, 253)
PlayerESP.Position = UDim2.new(0.0424405746, 0, 0.535481751, 0)
PlayerESP.Selectable = false
PlayerESP.Size = UDim2.new(0, 140, 0, 20)
PlayerESP.Font = Enum.Font.SourceSans
PlayerESP.Text = "Player ESP"
PlayerESP.TextColor3 = Color3.fromRGB(0, 0, 0)
PlayerESP.TextSize = 14.000

TextLabel.Parent = Frame
TextLabel.Active = true
TextLabel.BackgroundColor3 = Color3.fromRGB(119, 124, 127)
TextLabel.BackgroundTransparency = 1.000
TextLabel.BorderColor3 = Color3.fromRGB(119, 124, 127)
TextLabel.Position = UDim2.new(0.327688575, 0, 0.190135613, 0)
TextLabel.Size = UDim2.new(0, 50, 0, 20)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "STN GUI"
TextLabel.TextColor3 = Color3.fromRGB(187, 255, 253)
TextLabel.TextSize = 14.000
TextLabel.TextStrokeColor3 = Color3.fromRGB(187, 255, 253)
TextLabel.TextWrapped = true

-- Scripts:

RelicESP.MouseButton1Down:connect(function()

for i,v in pairs(game:GetService("Workspace").TempMap.Main.Relics:GetChildren()) do
if v.ClassName == "Relic" or v:IsA("MeshPart") then

local function addGui(part)
if v:FindFirstChild("STNESP") ~= nil then
v:FindFirstChild("STNESP"):Destroy()
print("Removing old ESP on " .. part.parent.Name)
end

local gui = Instance.new("BillboardGui", part)
gui.Name = "STNESP"
gui.Size = UDim2.new(1, 0, 1, 0)
gui.AlwaysOnTop = true

local frame = Instance.new("Frame", gui)
frame.Size = UDim2.new(3, 0, 3, 0)
frame.BackgroundTransparency = 0.5
frame.BorderSizePixel = 0

if part.parent.Name == "Relic" then
frame.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
end

print("Added ESP to " .. part.parent.Name .. "!")
end
addGui(v)
end
end
end)

RelicAura.MouseButton1Down:connect(function()

if game:GetService("Workspace").TempMap.Main.Relics.Relic then
for i = 1,100 do
for i,v in pairs(game:GetService("Workspace").TempMap.Main.Relics:GetChildren()) do
if v.Name == "Relic" then
fireproximityprompt(v.RelicPrompt)
end
end
end
end
end)

InstantBuild.MouseButton1Down:connect(function()

for i = 1,100 do
for i,v in pairs(game:GetService("Workspace").Misc:GetDescendants()) do
if v.Name == "BarricadePrompt" then
fireproximityprompt(v)
end
end
end
end)

PlayerESP.MouseButton1Down:connect(function()

--// Made by Blissful#4992 <-- Credits for the Box Esp by this guy.
--// Locals:
local workspace = game:GetService("Workspace")
local player = game:GetService("Players").LocalPlayer
local camera = workspace.CurrentCamera

--// Settings:
local on = true -- Use this if your making gui

local Box_Color = Color3.fromRGB(255, 0, 0)
local Box_Thickness = 2
local Box_Transparency = 1 -- 1 Visible, 0 Not Visible

local Tracers = true
local Tracer_Color = Color3.fromRGB(255, 0, 0)
local Tracer_Thickness = 2
local Tracer_Transparency = 1 -- 1 Visible, 0 Not Visible

local Autothickness = true -- Makes screen less encumbered

local Team_Check = true
local red = Color3.fromRGB(227, 52, 52)
local green = Color3.fromRGB(88, 217, 24)

local function NewLine()
local line = Drawing.new("Line")
line.Visible = false
line.From = Vector2.new(0, 0)
line.To = Vector2.new(1, 1)
line.Color = Box_Color
line.Thickness = Box_Thickness
line.Transparency = Box_Transparency
return line
end

--// Main Function:
for i, v in pairs(game.Players:GetChildren()) do
--// Lines for 3D box (12)
local lines = {
line1 = NewLine(),
line2 = NewLine(),
line3 = NewLine(),
line4 = NewLine(),
line5 = NewLine(),
line6 = NewLine(),
line7 = NewLine(),
line8 = NewLine(),
line9 = NewLine(),
line10 = NewLine(),
line11 = NewLine(),
line12 = NewLine(),
Tracer = NewLine()
}

lines.Tracer.Color = Tracer_Color
lines.Tracer.Thickness = Tracer_Thickness
lines.Tracer.Transparency = Tracer_Transparency

--// Updates ESP (lines) in render loop
local function ESP()
local connection
connection = game:GetService("RunService").RenderStepped:Connect(function()
if on and v.Character ~= nil and v.Character:FindFirstChild("Humanoid") ~= nil and v.Character:FindFirstChild("HumanoidRootPart") ~= nil and v.Name ~= player.Name and v.Character.Humanoid.Health > 0 and v.Character:FindFirstChild("Head") ~= nil then
local pos, vis = camera:WorldToViewportPoint(v.Character.HumanoidRootPart.Position)
if vis then
local Scale = v.Character.Head.Size.Y/2
local Size = Vector3.new(2, 3, 1.5) * (Scale * 2) -- Change this for different box size

local Top1 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, Size.Y, -Size.Z)).p)
local Top2 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, Size.Y, Size.Z)).p)
local Top3 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, Size.Y, Size.Z)).p)
local Top4 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, Size.Y, -Size.Z)).p)

local Bottom1 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, -Size.Y, -Size.Z)).p)
local Bottom2 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, -Size.Y, Size.Z)).p)
local Bottom3 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, -Size.Y, Size.Z)).p)
local Bottom4 = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, -Size.Y, -Size.Z)).p)

--// Top:
lines.line1.From = Vector2.new(Top1.X, Top1.Y)
lines.line1.To = Vector2.new(Top2.X, Top2.Y)

lines.line2.From = Vector2.new(Top2.X, Top2.Y)
lines.line2.To = Vector2.new(Top3.X, Top3.Y)

lines.line3.From = Vector2.new(Top3.X, Top3.Y)
lines.line3.To = Vector2.new(Top4.X, Top4.Y)

lines.line4.From = Vector2.new(Top4.X, Top4.Y)
lines.line4.To = Vector2.new(Top1.X, Top1.Y)

--// Bottom:
lines.line5.From = Vector2.new(Bottom1.X, Bottom1.Y)
lines.line5.To = Vector2.new(Bottom2.X, Bottom2.Y)

lines.line6.From = Vector2.new(Bottom2.X, Bottom2.Y)
lines.line6.To = Vector2.new(Bottom3.X, Bottom3.Y)

lines.line7.From = Vector2.new(Bottom3.X, Bottom3.Y)
lines.line7.To = Vector2.new(Bottom4.X, Bottom4.Y)

lines.line8.From = Vector2.new(Bottom4.X, Bottom4.Y)
lines.line8.To = Vector2.new(Bottom1.X, Bottom1.Y)

--//S ides:
lines.line9.From = Vector2.new(Bottom1.X, Bottom1.Y)
lines.line9.To = Vector2.new(Top1.X, Top1.Y)

lines.line10.From = Vector2.new(Bottom2.X, Bottom2.Y)
lines.line10.To = Vector2.new(Top2.X, Top2.Y)

lines.line11.From = Vector2.new(Bottom3.X, Bottom3.Y)
lines.line11.To = Vector2.new(Top3.X, Top3.Y)

lines.line12.From = Vector2.new(Bottom4.X, Bottom4.Y)
lines.line12.To = Vector2.new(Top4.X, Top4.Y)

--// Tracer:
if Tracers then
local trace = camera:WorldToViewportPoint((v.Character.HumanoidRootPart.CFrame * CFrame.new(0, -Size.Y, 0)).p)

lines.Tracer.From = Vector2.new(camera.ViewportSize.X/2, camera.ViewportSize.Y)
lines.Tracer.To = Vector2.new(trace.X, trace.Y)
end

--// Teamcheck:
if Team_Check then
if v.TeamColor == player.TeamColor then
for u, x in pairs(lines) do
x.Color = green
end
else
for u, x in pairs(lines) do
x.Color = red
end
end
end

--// Autothickness:
if Autothickness then
local distance = (player.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude
local value = math.clamp(1/distance*100, 0.1, 4) --0.1 is min thickness, 6 is max
for u, x in pairs(lines) do
x.Thickness = value
end
else
for u, x in pairs(lines) do
x.Thickness = Box_Thickness
end
end

for u, x in pairs(lines) do
if x ~= lines.Tracer then
x.Visible = true
end
end
if Tracers then
lines.Tracer.Visible = true
end
else
for u, x in pairs(lines) do
x.Visible = false
end
end
else
for u, x in pairs(lines) do
x.Visible = false
end
if game.Players:FindFirstChild(v.Name) == nil then
connection:Disconnect()
end
end
end)
end
coroutine.wrap(ESP)()
end

game.Players.PlayerAdded:Connect(function(newplr)
--// Lines for 3D box (12)
local lines = {
line1 = NewLine(),
line2 = NewLine(),
line3 = NewLine(),
line4 = NewLine(),
line5 = NewLine(),
line6 = NewLine(),
line7 = NewLine(),
line8 = NewLine(),
line9 = NewLine(),
line10 = NewLine(),
line11 = NewLine(),
line12 = NewLine(),
Tracer = NewLine()
}

lines.Tracer.Color = Tracer_Color
lines.Tracer.Thickness = Tracer_Thickness
lines.Tracer.Transparency = Tracer_Transparency

--// Updates ESP (lines) in render loop
local function ESP()
local connection
connection = game:GetService("RunService").RenderStepped:Connect(function()
if on and newplr.Character ~= nil and newplr.Character:FindFirstChild("Humanoid") ~= nil and newplr.Character:FindFirstChild("HumanoidRootPart") ~= nil and newplr.Name ~= player.Name and newplr.Character.Humanoid.Health > 0 and newplr.Character:FindFirstChild("Head") ~= nil then
local pos, vis = camera:WorldToViewportPoint(newplr.Character.HumanoidRootPart.Position)
if vis then
local Scale = newplr.Character.Head.Size.Y/2
local Size = Vector3.new(2, 3, 1.5) * (Scale * 2) -- Change this for different box size

local Top1 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, Size.Y, -Size.Z)).p)
local Top2 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, Size.Y, Size.Z)).p)
local Top3 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, Size.Y, Size.Z)).p)
local Top4 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, Size.Y, -Size.Z)).p)

local Bottom1 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, -Size.Y, -Size.Z)).p)
local Bottom2 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(-Size.X, -Size.Y, Size.Z)).p)
local Bottom3 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, -Size.Y, Size.Z)).p)
local Bottom4 = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(Size.X, -Size.Y, -Size.Z)).p)

--// Top:
lines.line1.From = Vector2.new(Top1.X, Top1.Y)
lines.line1.To = Vector2.new(Top2.X, Top2.Y)

lines.line2.From = Vector2.new(Top2.X, Top2.Y)
lines.line2.To = Vector2.new(Top3.X, Top3.Y)

lines.line3.From = Vector2.new(Top3.X, Top3.Y)
lines.line3.To = Vector2.new(Top4.X, Top4.Y)

lines.line4.From = Vector2.new(Top4.X, Top4.Y)
lines.line4.To = Vector2.new(Top1.X, Top1.Y)

--// Bottom:
lines.line5.From = Vector2.new(Bottom1.X, Bottom1.Y)
lines.line5.To = Vector2.new(Bottom2.X, Bottom2.Y)

lines.line6.From = Vector2.new(Bottom2.X, Bottom2.Y)
lines.line6.To = Vector2.new(Bottom3.X, Bottom3.Y)

lines.line7.From = Vector2.new(Bottom3.X, Bottom3.Y)
lines.line7.To = Vector2.new(Bottom4.X, Bottom4.Y)

lines.line8.From = Vector2.new(Bottom4.X, Bottom4.Y)
lines.line8.To = Vector2.new(Bottom1.X, Bottom1.Y)

--//S ides:
lines.line9.From = Vector2.new(Bottom1.X, Bottom1.Y)
lines.line9.To = Vector2.new(Top1.X, Top1.Y)

lines.line10.From = Vector2.new(Bottom2.X, Bottom2.Y)
lines.line10.To = Vector2.new(Top2.X, Top2.Y)

lines.line11.From = Vector2.new(Bottom3.X, Bottom3.Y)
lines.line11.To = Vector2.new(Top3.X, Top3.Y)

lines.line12.From = Vector2.new(Bottom4.X, Bottom4.Y)
lines.line12.To = Vector2.new(Top4.X, Top4.Y)

--// Tracer:
if Tracers then
local trace = camera:WorldToViewportPoint((newplr.Character.HumanoidRootPart.CFrame * CFrame.new(0, -Size.Y, 0)).p)
lines.Tracer.From = Vector2.new(camera.ViewportSize.X/2, camera.ViewportSize.Y)
lines.Tracer.To = Vector2.new(trace.X, trace.Y)
end

--// Teamcheck:
if Team_Check then
if newplr.TeamColor == player.TeamColor then
for u, x in pairs(lines) do
x.Color = green
end
else
for u, x in pairs(lines) do
x.Color = red
end
end
end

--// Autothickness:
if Autothickness then
local distance = (player.Character.HumanoidRootPart.Position - newplr.Character.HumanoidRootPart.Position).magnitude
local value = math.clamp(1/distance*100, 0.1, 4) --0.1 is min thickness, 6 is max
for u, x in pairs(lines) do
x.Thickness = value
end
else
for u, x in pairs(lines) do
x.Thickness = Box_Thickness
end
end

for u, x in pairs(lines) do
if x ~= lines.Tracer then
x.Visible = true
end
end
if Tracers then
lines.Tracer.Visible = true
end
else
for u, x in pairs(lines) do
x.Visible = false
end
end
else
for u, x in pairs(lines) do
x.Visible = false
end
if game.Players:FindFirstChild(newplr.Name) == nil then
connection:Disconnect()
end
end
end)
end
coroutine.wrap(ESP)()
end)

function Create(base, team)
local bb = Instance.new('BillboardGui', game.CoreGui)
bb.Adornee = base
bb.ExtentsOffset = Vector3.new(0,1,0)
bb.AlwaysOnTop = true
bb.Size = UDim2.new(0,5,0,5)
bb.StudsOffset = Vector3.new(0,1,0)
bb.Name = 'tracker'
local frame = Instance.new('Frame',bb)
frame.ZIndex = 10
frame.BackgroundTransparency = 0.3
frame.Size = UDim2.new(1,0,1,0)
local txtlbl = Instance.new('TextLabel',bb)
txtlbl.ZIndex = 10
txtlbl.BackgroundTransparency = 1
txtlbl.Position = UDim2.new(0,0,0,-35)
txtlbl.Size = UDim2.new(1,0,10,0)
txtlbl.Font = 'ArialBold'
txtlbl.FontSize = 'Size12'
txtlbl.Text = base.Parent.Name:upper()
txtlbl.TextStrokeTransparency = 0.5
if team then
txtlbl.TextColor3 = Color3.new(0,1,1)
frame.BackgroundColor3 = Color3.new(0,1,1)
else
txtlbl.TextColor3 = Color3.new(1,0,0)
frame.BackgroundColor3 = Color3.new(1,0,0)
end
end

function Clear()
for _,v in pairs(game.CoreGui:children()) do
if v.Name == 'tracker' and v:isA('BillboardGui') then
v:Destroy()
end
end
end

function Find()
Clear()
track = true
spawn(function()
while wait(1) do
if track then
Clear()
for _,v in pairs(game.Players:GetChildren()) do
if v.Name ~= game.Players.LocalPlayer.Name then
if v.Character and v.Character.Head then
Create(v.Character.Head, false)
end
end
end
end
wait(1)
end
end)
end

Find()
end)
