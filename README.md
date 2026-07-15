-- File: Loader.lua
local player = game.Players.LocalPlayer
local screenGui = Instance.new("ScreenGui", player.PlayerGui)
local frame = Instance.new("Frame", screenGui)
frame.Size = UDim2.new(0, 200, 0, 100)
frame.Position = UDim2.new(0.5, -100, 0.5, -50)
frame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
frame.Active = true
frame.Draggable = true

local input = Instance.new("TextBox", frame)
input.Size = UDim2.new(0.8, 0, 0.4, 0)
input.Position = UDim2.new(0.1, 0, 0.1, 0)
input.PlaceholderText = "Enter Key"

local button = Instance.new("TextButton", frame)
button.Size = UDim2.new(0.8, 0, 0.3, 0)
button.Position = UDim2.new(0.1, 0, 0.6, 0)
button.Text = "Submit"

button.MouseButton1Click:Connect(function()
    if input.Text == "KEYFREE" then
        screenGui:Destroy()
        -- Tự động chạy script chính sau khi nhập đúng KEY
        loadstring(game:HttpGet("https://raw.githubusercontent.com/caomod2077/Script/refs/heads/main/FN_AnimalHospital.lua"))()
    else
        input.Text = "Wrong Key!"
        task.wait(1)
        input.Text = ""
    end
end)
