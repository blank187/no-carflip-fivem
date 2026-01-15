Hey there a quick and easy way to prevent your players from flipping a car that is stuck on its roof - either download the file and add it to an existing resource or make a resource for itself. Clientside!

CreateThread(function()
    while true do
        Wait(0)
        local ped = PlayerPedId()
        if IsPedInAnyVehicle(ped, false) then
            local vehicle = GetVehiclePedIsIn(ped, false)
            local roll = GetEntityRoll(vehicle)
            if (roll > 75.0 or roll < -75.0) and GetEntitySpeed(vehicle) < 2 then
                DisableControlAction(2, 59, true) -- Disable left/right
                DisableControlAction(2, 60, true) -- Disable up/down
            end
        end
    end
end)
