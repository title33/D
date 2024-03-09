local speed = -387
local boostActive = false

function activateBoost()
    boostActive = true
end

function deactivateBoost()
    boostActive = false
end

vehicleloopspeed = game:GetService("RunService").Stepped:Connect(function()
    if boostActive and Humanoid:IsA("Humanoid") then
        Humanoid.SeatPart:ApplyImpulse(Humanoid.SeatPart.CFrame.LookVector * Vector3.new(speed, speed, speed))
    end
end)
