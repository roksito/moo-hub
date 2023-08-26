
local function press(a)
    game:GetService("VirtualInputManager"):SendKeyEvent(true, tostring(a), false, game)
end
-- test
_G.autofarm = false;
_G.stats = false;
_G.trade = false;
_G.tradescam = false;
getgenv().Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/RTrade/Voidz/main/API/Networks/swordhook-network.lua"))() --you can go into the github link and copy all of it and modify it for yourself.
getgenv().Window = getgenv().Library:CreateWindow('Palm Slap Friends Simulator', Vector2.new(550, 627), Enum.KeyCode.LeftShift) 

local Test = Window:CreateTab("main")
local Test2 = Test:CreateSector("farm tab","left")
local hi = Window:CreateTab("TESTING TAB")
local hie = Window:CreateTab("mics")
local he = hi:CreateSector("beta","left")
local hea = hie:CreateSector("Mics","left")
he:AddDropdown("select boss",{"1", "2", "3", "4", "5", "6","7","8", "9","10"},false,function(choice)
local farm = choise
    end)
hea:AddToggle("trade scam?",false,function(state)
getgenv().tradescam = state
while getgenv().tradescam do
wait(0.05)
   for _, v in pairs(game:GetService("Players"):GetPlayers()) do
       if v.Name ~= game:GetService("Players").LocalPlayer.Name then

            local args = {
    [1] = v,
    [2] = {},
    [3] = 0,
    [4] = false
}

game:GetService("ReplicatedStorage"):WaitForChild("ModuleScript"):WaitForChild("Trading_System"):WaitForChild("TradingStateing"):FireServer(unpack(args))

         
      end
   end

end
end)
hea:AddToggle("trade all[annoying]",false,function(state)
getgenv().trade = state
while getgenv().trade do
wait(0.05)
   for _, v in pairs(game:GetService("Players"):GetPlayers()) do
       if v.Name ~= game:GetService("Players").LocalPlayer.Name then

            local args = {
    [1] = v
}

game:GetService("ReplicatedStorage"):WaitForChild("ModuleScript"):WaitForChild("Trading_System"):WaitForChild("RemoteEvent"):FireServer(unpack(args))

         
      end
   end

end
end)
Test2:AddToggle("auto slap[faster]",false,function(state)
getgenv().autofarm = state
while getgenv().autofarm do
wait(0.05)
local args = {
    [1] = true
}

game:GetService("ReplicatedStorage"):WaitForChild("Event"):WaitForChild("TakeDamgeEvent"):FireServer(unpack(args))

end
end)



Test2:AddToggle("auto giver",false,function(state)
getgenv().stats = state
while getgenv().stats do
wait(0.05)
local args = {
    [1] = "palm",
    [2] = 3,
    [3] = "7"
}

game:GetService("ReplicatedStorage"):WaitForChild("Event"):WaitForChild("ToolAttack"):FireServer(unpack(args))
wait()
local args = {
    [1] = "Neck",
    [2] = 3,
    [3] = "12"
}

game:GetService("ReplicatedStorage"):WaitForChild("Event"):WaitForChild("ToolAttack"):FireServer(unpack(args))
wait()
local args = {
    [1] = "Power",
    [2] = 3,
    [3] = "12"
}

game:GetService("ReplicatedStorage"):WaitForChild("Event"):WaitForChild("ToolAttack"):FireServer(unpack(args))

end
end)

Test2:AddButton("copy discord",function()
setclipboard("https://discord.gg/seeVXSzH")
end)
