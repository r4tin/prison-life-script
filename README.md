local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("hub prison life by Batatox#5550", "Ocean")
local Tab = Window:NewTab("home")
local Section = Tab:NewSection("")
local Tab = Window:NewTab("Armas")
local Section = Tab:NewSection("")
Section:NewButton("Get Remington 870", "aperta para pegar a arma", function()
    local args = {
    [1] = workspace.Prison_ITEMS.giver["Remington 870"].ITEMPICKUP
}

Section:NewButton("Get Ak 47", "ButtonInfo", function()
    local args = {
    [1] = workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP
}

workspace.Remote.ItemHandler:InvokeServer(unpack(args))

end)
workspace.Remote.ItemHandler:InvokeServer(unpack(args))

end)

local Tab = Window:NewTab("Scripts kill e etc")
local Section = Tab:NewSection("")
Section:NewTextBox("Tp", "coloque o nome da pessoa pra dar tp.", function(txt)
    for i, v in pairs(game.Players:GetPlayers()) do
          if v.Name == txt or v.DisplayName == txt and v.Character then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame
    end
  end
end)
Section:NewButton("Kill all legit", "Para desativar é so resetar.", function()
    getgenv().a = true
while getgenv().a and wait() do
    for i, v in pairs(game.Players:GetPlayers()) do
        if v.Character and v ~= game.Players.LocalPlayer and v.Team.Name ~= "Neutral" and v.Character:WaitForChild("Humanoid").Health ~= 0 and not v.Character:FindFirstChild("ForceField") then
            local args = {
                [1] = v
            }
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame
            game:GetService("ReplicatedStorage").meleeEvent:FireServer(unpack(args))
        end
    end
end
end)
