# ScriptcodeR
Admin script for roblox (Only for games)


-- Admin Commands Script

local prefix = ":" -- Change this to your desired prefix

local function onChat(message, sender)

    local lowerMessage = message:lower()

    -- Check if the message starts with the prefix

    if lowerMessage:sub(1, #prefix) == prefix then

        -- Remove the prefix from the message

        local command = lowerMessage:sub(#prefix + 1)

        -- Check the command and execute the corresponding action

        if command == "kill all" then

            game.Players:ClearAllChildren()

            print("All players have been killed.")

        elseif command == "loopkillall" then

            while wait() do

                game.Players:ClearAllChildren()

                print("All players have been killed.")

            end

        elseif command == "ff" then

            for _, player in ipairs(game.Players:GetPlayers()) do

                player:EnableFriendlyFire(true)

            end

            print("Friendly fire has been enabled.")

        elseif command == "unff" then

            for _, player in ipairs(game.Players:GetPlayers()) do

                player:EnableFriendlyFire(false)

            end

            print("Friendly fire has been disabled.")

        elseif command == "fly" then

            local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")

            if humanoid then

                humanoid.PlatformStand = true

                print("You can now fly.")

            end

        elseif command == "fire" then

            for _, player in ipairs(game.Players:GetPlayers()) do

                local character = player.Character

                if character then

                    local humanoid = character:FindFirstChildOfClass("Humanoid")

                    if humanoid then

                        local fire = Instance.new("Fire")

                        fire.Parent = character

                        fire.Size = 5

                        fire.Heat = 10

                        fire.Burnt.Value = false

                        print(player.Name .. " has been set on fire.")

                    end

                end

            end

        elseif command == "mute" then

            for _, player in ipairs(game.Players:GetPlayers()) do

                local gui = player.PlayerGui:FindFirstChild("Chat")

                if gui then

                    gui.Enabled = false

                    print(player.Name .. " has been muted.")

                end

            end

        else

            print("Unknown command: " .. command)

        end

    end

end

game.Players.PlayerAdded:Connect(function(player)

    player.Chatted:Connect(function(message)

        onChat(message, player)

    end)

end)

To use this script, create a new Script object in Roblox Studio and paste the code inside it. You can modify the prefix variable at the beginning of the script to change the command prefix if desired. Make sure to save the script and publish your game to see the admin commands in action.

Please note that this script provides basic functionality for the requested commands and doesn't include any security measures. Remember to use admin commands responsibly and consider adding permission checks or additional validation as needed to prevent misuse or abuse.

To use this script, create a new Script object in Roblox Studio and paste the code inside it. You can modify the prefix variable at the beginning of the script to change the command prefix if desired. Make sure to save the script and publish your game to see the admin commands in action.

Please note that this script provides basic functionality for the requested commands and doesn't include any security measures. Remember to use admin commands responsibly and consider adding permission checks or additional validation as needed to prevent misuse or abuse.

Please remember to just copy the script, don't be retard 
