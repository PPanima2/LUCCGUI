local Players = game:GetService("Players")
local Lighting = game:GetService("Lighting")

local player = Players.LocalPlayer
local screenGui = script.Parent

local céusButton = screenGui.MenuFrame:WaitForChild("CéusButton")
local noiteButton = screenGui.MenuFrame:WaitForChild("NoiteButton")

céusButton.MouseButton1Click:Connect(function()
    print("Ó céus clicado!")
    céusButton.Text = "Ai meu Deus!"
end)

noiteButton.MouseButton1Click:Connect(function()
    Lighting.ClockTime = 20 -- muda o céu para noite
end)
local explosion = Instance.new("Explosion")
explosion.Position = player.Character.HumanoidRootPart.Position
explosion.Parent = workspace
player.Character.Humanoid.WalkSpeed = 100
for _, part in pairs(player.Character:GetDescendants()) do
    if part:IsA("BasePart") then
        part.Transparency = 1
    end
end
Lighting.ClockTime = 12
SkyboxBk = "rbxassetid://159454299"
SkyboxDn = "rbxassetid://159454296"
SkyboxFt = "rbxassetid://159454293"
SkyboxLf = "rbxassetid://159454286"
SkyboxRt = "rbxassetid://159454300"
SkyboxUp = "rbxassetid://159454288"
player.Character:SetPrimaryPartCFrame(player.Character.PrimaryPart.CFrame * CFrame.Angles(0, math.rad(90), 0))
local particle = Instance.new("ParticleEmitter")
particle.Texture = "rbxassetid://243660364" -- estrela por exemplo
particle.Rate = 50
particle.Parent = player.Character.Head
