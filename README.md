--[[
This script made by 5fr3
Credits to 5fr3
]]

-- تشغيل سكربت FakeDash الأصلي
loadstring(game:HttpGet(
"https://raw.githubusercontent.com/Cyborg883/FakeDash/refs/heads/main/Protected_5833389828844912.lua"
))()

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local player = Players.LocalPlayer

local TARGET_IMAGE = "rbxassetid://18274894738"

local function moveFakeDashByImage()
local guis = {
player:WaitForChild("PlayerGui"),
game:GetService("CoreGui")
}

for _, gui in ipairs(guis) do  
    for _, v in ipairs(gui:GetDescendants()) do  
        if (v:IsA("ImageButton") or v:IsA("ImageLabel")) then  
            if v.Image == TARGET_IMAGE then  
                v.AnchorPoint = Vector2.new(0.5, 0.5)  

                if UIS.TouchEnabled then  
                    -- 👈 المكان اللي انت عايزه  
                    v.Position = UDim2.new(0.09, 0, 0.49, 0)  
                end  
            end  
        end  
    end  
end

end

-- استنى السكربت يحمّل
task.wait(1)
moveFakeDashByImage()

-- لو اتعمل بعد شوية
player.PlayerGui.DescendantAdded:Connect(function()
task.wait(0.2)
moveFakeDashByImage()
end)
