repeat wait() until game:IsLoaded()
local LoadingTime = tick();

local localPlayer = game.Players.LocalPlayer


game:GetService("RunService").Heartbeat:Connect(function()
    if localPlayer.Character and localPlayer.Character:FindFirstChild("Humanoid") then
        oldState = currentState
        currentState = localPlayer.Character.Humanoid:GetState()
    end
end)

local userInputService = game:GetService("UserInputService")

LPH_NO_VIRTUALIZE = function(a) return a end
LPH_NO_UPVALUES = function(a) return a end


------------------------------------ VARS -----------------------------------
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/wrrexk/Astralis/refs/heads/main/Main/Astralis%20Lib.lua"))()
local Wait = library.subs.Wait
local userInputService = game:GetService("UserInputService")
local replicatedStorage = game:GetService("ReplicatedStorage")
local runService = game:GetService("RunService")
local players = game:GetService("Players")
local lighting = game:GetService("Lighting")
local localPlayer = players.LocalPlayer
local camera = workspace.CurrentCamera
local mouse = localPlayer:GetMouse()
local debris = game:GetService("Debris")
local client = getsenv(localPlayer.PlayerGui.Client)


local lines = {} 
local AstralisLuaScripts = {}

local SkyboxesTable = {
    "Default", "Galaxy", "Pink Sky", "Sunset", "Night", "Evening", "Purple Nebula", 
    "Night Sky", "Pink Daylight", "Morning Glow", "Setting Sun", "Elegant Morning", "Neptune", "Redshift", "Aesthetic Night"
}

local KnivesTable = {
    "WIP"
}

local GlovesTable = {
    "WIP"
}

local SkinsTable = {
    "WIP"
}

local SkyboxesPresets = {
    ["Default"] = {
        SkyboxBk = "rbxassetid://153695414",
        SkyboxDn = "rbxassetid://153695352",
        SkyboxFt = "rbxassetid://153695452",
        SkyboxLf = "rbxassetid://153695320",
        SkyboxRt = "rbxassetid://153695383",
        SkyboxUp = "rbxassetid://153695471"
    },
    ["Galaxy"] = {
        SkyboxBk = "http://www.roblox.com/asset/?id=159454299",
        SkyboxDn = "http://www.roblox.com/asset/?id=159454296",
        SkyboxFt = "http://www.roblox.com/asset/?id=159454293",
        SkyboxLf = "http://www.roblox.com/asset/?id=159454286",
        SkyboxRt = "http://www.roblox.com/asset/?id=159454300",
        SkyboxUp = "http://www.roblox.com/asset/?id=159454288"
    },
    ["Pink Sky"] = {
        SkyboxLf = "rbxassetid://271042310",
		SkyboxBk = "rbxassetid://271042516",
		SkyboxDn = "rbxassetid://271077243",
		SkyboxFt = "rbxassetid://271042556",
		SkyboxRt = "rbxassetid://271042467",
		SkyboxUp = "rbxassetid://271077958"
    },
    ["Sunset"] = {
        SkyboxBk = "http://www.roblox.com/asset/?id=458016711",
        SkyboxDn = "http://www.roblox.com/asset/?id=458016826",
        SkyboxFt = "http://www.roblox.com/asset/?id=458016532",
        SkyboxLf = "http://www.roblox.com/asset/?id=458016655",
        SkyboxRt = "http://www.roblox.com/asset/?id=458016782",
        SkyboxUp = "http://www.roblox.com/asset/?id=458016792"
    },
    ["Night"] = {
        SkyboxBk = "rbxassetid://48020371",
        SkyboxDn = "rbxassetid://48020144",
        SkyboxFt = "rbxassetid://48020234",
        SkyboxLf = "rbxassetid://48020211",
        SkyboxRt = "rbxassetid://48020254",
        SkyboxUp = "rbxassetid://48020383"
    },
    ["Evening"] = {
        SkyboxLf = "http://www.roblox.com/asset/?id=7950573918",
        SkyboxBk = "http://www.roblox.com/asset/?id=7950569153",
		SkyboxDn = "http://www.roblox.com/asset/?id=7950570785",
		SkyboxFt = "http://www.roblox.com/asset/?id=7950572449",
		SkyboxRt = "http://www.roblox.com/asset/?id=7950575055",
	    SkyboxUp = "http://www.roblox.com/asset/?id=7950627627"
    },
    ["Purple Nebula"] = {
        SkyboxBk = "rbxassetid://159454299",
            SkyboxDn = "rbxassetid://159454296",
            SkyboxFt = "rbxassetid://159454293",
            SkyboxLf = "rbxassetid://159454286",
            SkyboxRt = "rbxassetid://159454300",
            SkyboxUp = "rbxassetid://159454288"
    },
    ["Night Sky"] = {
            SkyboxBk = "rbxassetid://12064107",
            SkyboxDn = "rbxassetid://12064152",
            SkyboxFt = "rbxassetid://12064121",
            SkyboxLf = "rbxassetid://12063984",
            SkyboxRt = "rbxassetid://12064115",
            SkyboxUp = "rbxassetid://12064131"
    },
    ["Pink Daylight"] = {
            SkyboxBk = "rbxassetid://271042516",
            SkyboxDn = "rbxassetid://271077243",
            SkyboxFt = "rbxassetid://271042556",
            SkyboxLf = "rbxassetid://271042310",
            SkyboxRt = "rbxassetid://271042467",
            SkyboxUp = "rbxassetid://271077958"
    },
    ["Morning Glow"] = {
            SkyboxBk = "rbxassetid://1417494030",
            SkyboxDn = "rbxassetid://1417494146",
            SkyboxFt = "rbxassetid://1417494253",
            SkyboxLf = "rbxassetid://1417494402",
            SkyboxRt = "rbxassetid://1417494499",
            SkyboxUp = "rbxassetid://1417494643"
    },
    ["Setting Sun"] = {
            SkyboxBk = "rbxassetid://626460377",
            SkyboxDn = "rbxassetid://626460216",
            SkyboxFt = "rbxassetid://626460513",
            SkyboxLf = "rbxassetid://626473032",
            SkyboxRt = "rbxassetid://626458639",
            SkyboxUp = "rbxassetid://626460625"
    },
    ["Elegant Morning"] = {
            SkyboxBk = "rbxassetid://153767241",
            SkyboxDn = "rbxassetid://153767216",
            SkyboxFt = "rbxassetid://153767266",
            SkyboxLf = "rbxassetid://153767200",
            SkyboxRt = "rbxassetid://153767231",
            SkyboxUp = "rbxassetid://153767288"
    },
    ["Neptune"] = {
            SkyboxBk = "rbxassetid://218955819",
            SkyboxDn = "rbxassetid://218953419",
            SkyboxFt = "rbxassetid://218954524",
            SkyboxLf = "rbxassetid://218958493",
            SkyboxRt = "rbxassetid://218957134",
            SkyboxUp = "rbxassetid://218950090"
    },
    ["Redshift"] = {
            SkyboxBk = "rbxassetid://401664839",
            SkyboxDn = "rbxassetid://401664862",
            SkyboxFt = "rbxassetid://401664960",
            SkyboxLf = "rbxassetid://401664881",
            SkyboxRt = "rbxassetid://401664901",
            SkyboxUp = "rbxassetid://401664936"
    },
    ["Aesthetic Night"] = {
            SkyboxBk = "rbxassetid://1045964490",
            SkyboxDn = "rbxassetid://1045964368",
            SkyboxFt = "rbxassetid://1045964655",
            SkyboxLf = "rbxassetid://1045964655",
            SkyboxRt = "rbxassetid://1045964655",
            SkyboxUp = "rbxassetid://1045962969"
     }
}


local AstralisWindow = library:CreateWindow({
    Name = "AstralisM | Private",
    Themeable = {
        Info = "Private (Beta)" 
    }
})

if not isfolder("Astralis//main/AstralisMLua") then
    makefolder("Astralis/main/AstralisMLua")
end
local directoryPath = "Astralis//main/AstralisMLua"

------------------------------------ TABS -----------------------------------

local MovementTab = AstralisWindow:CreateTab({
    Name = "Movement"
})

local MiscTab = AstralisWindow:CreateTab({
    Name = "Misc"
})

local SkinsTab = AstralisWindow:CreateTab({
    Name = "Skins"
})

local LuaTab = AstralisWindow:CreateTab({
    Name = "Lua"
})

------------------------------------ FLAGS -----------------------------------

local localPlayer = game.Players.LocalPlayer
local horizontalLayoutFrame = Instance.new("Frame")
horizontalLayoutFrame.Parent = WorldSection
horizontalLayoutFrame.Size = UDim2.new(1, 0, 0, 40) 
local uiListLayout = Instance.new("UIListLayout")
uiListLayout.Parent = horizontalLayoutFrame
uiListLayout.FillDirection = Enum.FillDirection.Horizontal
uiListLayout.Padding = UDim.new(0, 10) 
local ebCooldown = false
local oldState, currentState
local selectedFile = nil
local SkyboxToggleActive = false
local OriginalSkybox = nil
local oldAmbient = lighting.Ambient
local oldOutdoorAmbient = lighting.OutdoorAmbient
local container = Instance.new("Frame")
container.Size = UDim2.new(1, 0, 0, 40)  
container.Parent = WorldSection

local flags = {
    bunny_hop = false,    
    bhop_speed = 150,     
    drawing_enabled = false,
    velo_graph = false,
    velo_indicator = false,
    wasd_indicator = false,
    graph_width = 1,
    ambience = false, 
    Indoor_ambience_color = Color3.new(1, 1, 1),  
    Outdoor_ambience_color = Color3.new(1, 1, 1),
    edge_bug = false, 
    eb_bind = Enum.KeyCode.Space,
    inf_cash = false ,
    hitsound_enabled = false,
    hitsound_value = "Bameware",
    hitsound_volume = 2 

}
------------------------------------ FIXES FOR SCRIPTS -----------------------------------

local veloIndicator = Drawing.new("Text") 
veloIndicator.Color = Color3.new(1, 1, 1) 
veloIndicator.Size = 18 
veloIndicator.Visible = true  

local wIndicator = Drawing.new("Text")
wIndicator.Color = Color3.new(1, 1, 1)  
wIndicator.Size = 18  
wIndicator.Visible = true  

local aIndicator = Drawing.new("Text")
aIndicator.Color = Color3.new(1, 1, 1)
aIndicator.Size = 18
aIndicator.Visible = true

local sIndicator = Drawing.new("Text")
sIndicator.Color = Color3.new(1, 1, 1)
sIndicator.Size = 18
sIndicator.Visible = true

local dIndicator = Drawing.new("Text")
dIndicator.Color = Color3.new(1, 1, 1)
dIndicator.Size = 18
dIndicator.Visible = true

local spaceIndicator = Drawing.new("Text")
spaceIndicator.Color = Color3.new(1, 1, 1)
spaceIndicator.Size = 18
spaceIndicator.Visible = true

local ctrlIndicator = Drawing.new("Text")
ctrlIndicator.Color = Color3.new(1, 1, 1)
ctrlIndicator.Size = 18
ctrlIndicator.Visible = true


------------------------------------ FUNCTIONS -----------------------------------

local function isAlive()
    if localPlayer.Character and localPlayer.Character:FindFirstChild("Humanoid") then
        local humanoid = localPlayer.Character:FindFirstChild("Humanoid")
        return humanoid.Health > 0
    end
    return false
end

local function getLuaAndTxtFiles(directory)
    local files = {}
    local success, dirFiles = pcall(function()
        return listfiles(directory) 
    end)
    if success and dirFiles then
        for _, filePath in ipairs(dirFiles) do
            if filePath:match("%.lua$") or filePath:match("%.txt$") then
                table.insert(files, filePath:match("[^\\]+$")) 
            end
        end
    else
        library.Notify({
            Text = "Could not read directory: " .. directory,
            Duration = 5  
        })
    end
    return files
end


local function rejoinGame()
    library.Notify({
        Text = "Rejoining the game..."
    })

    local player = game.Players.LocalPlayer
    local placeId = game.PlaceId
    local teleportService = game:GetService("TeleportService")
    teleportService:Teleport(placeId, player)
end

local function copyJobID()
    local jobID = game.JobId 
    setclipboard(jobID) 
    library.Notify({
        Text = "Job ID copied: " .. jobID
    })
end

local function StartBunnyHop()
    while flags.bunny_hop do
        runService.RenderStepped:Wait()  
        
        if isAlive() and userInputService:IsKeyDown(Enum.KeyCode.Space) then
            localPlayer.Character.Humanoid.Jump = true  

            local speed = flags.bhop_speed 
            local dir = camera.CFrame.LookVector * Vector3.new(1, 0, 1)
            local move = Vector3.new() 
            
            if userInputService:IsKeyDown(Enum.KeyCode.W) then
                move = move + dir
            end
            if userInputService:IsKeyDown(Enum.KeyCode.S) then
                move = move - dir
            end
            if userInputService:IsKeyDown(Enum.KeyCode.D) then
                move = move + Vector3.new(-dir.Z, 0, dir.X)
            end
            if userInputService:IsKeyDown(Enum.KeyCode.A) then
                move = move + Vector3.new(dir.Z, 0, -dir.X)
            end

            if move.Unit.X == move.Unit.X then
                move = move.Unit  
                localPlayer.Character.HumanoidRootPart.Velocity = Vector3.new(
                    move.X * speed,  
                    localPlayer.Character.HumanoidRootPart.Velocity.Y,  
                    move.Z * speed  
                )
            end
        end
    end
end

local function StopBunnyHop()
end

local function StartDrawing()
    while flags.drawing_enabled do
        wait() 

        local normalY = camera.ViewportSize.Y - 90
        local alive = isAlive()
        local value = alive and math.floor(math.clamp((localPlayer.Character.HumanoidRootPart.Velocity * Vector3.new(1, 0, 1)).magnitude * 14.85, 0, 400)) or 0

        if flags.velo_graph then
            local width = flags.graph_width + 1
            local line = Drawing.new("Line")
            table.insert(lines, line)
            line.From = Vector2.new(camera.ViewportSize.X / 2 + (60 * width - width), lastPos)
            line.To = Vector2.new(camera.ViewportSize.X / 2 + 60 * width, normalY - value / 4)
            line.Thickness = 1
            line.Transparency = 1
            line.Color = Color3.new(1, 1, 1)
            line.Visible = true

            if #lines > 1 then
                if #lines > 110 then
                    lines[1]:Remove()
                    table.remove(lines, 1)
                    for i = 2, 8 do
                        lines[i].Transparency = i / 10
                    end
                    local count = 0
                    for i = 110, 110 - 6, -1 do
                        count = count + 1
                        lines[i].Transparency = count / 10
                    end
                    lines[110 - 7].Transparency = 1
                end
                for i, v in ipairs(lines) do
                    v.To = v.To - Vector2.new(width, 0)
                    v.From = v.From - Vector2.new(width, 0)
                end
            end

            lastPos = line.To.Y
        end

        if flags.velo_indicator then
            veloIndicator.Text = tostring(value)
            veloIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 75)
        end

        if flags.wasd_indicator then
            wIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 50)
            aIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 50) + Vector2.new(-40, 25)
            sIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 50) + Vector2.new(0, 25)
            dIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 50) + Vector2.new(40, 25)
            spaceIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 50) + Vector2.new(40, 0)
            ctrlIndicator.Position = Vector2.new(camera.ViewportSize.X / 2, camera.ViewportSize.Y - 50) + Vector2.new(-40, 0)

            wIndicator.Text = userInputService:IsKeyDown(Enum.KeyCode.W) and "W" or "-"
            aIndicator.Text = userInputService:IsKeyDown(Enum.KeyCode.A) and "A" or "-"
            sIndicator.Text = userInputService:IsKeyDown(Enum.KeyCode.S) and "S" or "-"
            dIndicator.Text = userInputService:IsKeyDown(Enum.KeyCode.D) and "D" or "-"
            spaceIndicator.Text = userInputService:IsKeyDown(Enum.KeyCode.Space) and "J" or "-"
            ctrlIndicator.Text = userInputService:IsKeyDown(Enum.KeyCode.LeftControl) and "C" or "-"
        end
    end
end

local function StopDrawing()
end

local function updateAmbienceColors()
    if flags.ambience then
        lighting.Ambient = flags.Indoor_ambience_color
        lighting.OutdoorAmbient = flags.Outdoor_ambience_color
    else
        lighting.Ambient = oldAmbient
        lighting.OutdoorAmbient = oldOutdoorAmbient
    end
end

local function isButtonDown(keyCode)
    return userInputService:IsKeyDown(keyCode)
end




------------------------------------ MOVEMENT -----------------------------------

local MovementSection = MovementTab:CreateSection({
    Name = "Movement Cheats",
    Side = "Left"
})

MovementSection:AddToggle({
    Name = "Bunny Hop", 
    Flag = "bunny_hop", 
    Keybind = { Mode = "Dynamic" },
    Value = flags.bunny_hop,  
    Callback = function(newValue, lastValue)
        flags.bunny_hop = newValue

        if flags.bunny_hop then
            StartBunnyHop() 
        else
            StopBunnyHop() 
        end
    end
})

MovementSection:AddSlider({
    Name = "Bhop Speed",  
    Min = 50,  
    Max = 500,  
    Default = flags.bhop_speed,
    Flag = "bhop_speed", 
    Callback = function(newValue)
        flags.bhop_speed = newValue
    end
})

MovementSection:AddToggle({
    Name = "Edge Bug",
    Flag = "edge_bug", 
    Value = flags.edge_bug, 
    Keybind = { Mode = "Dynamic" },
    Callback = function(newValue)
        flags.edge_bug = newValue 

        if flags.edge_bug then
            local function edgeBugLogic()
                if flags.edge_bug and not ebCooldown and isButtonDown(flags.eb_bind) then
                    if oldState == Enum.HumanoidStateType.Freefall and currentState == Enum.HumanoidStateType.Landed then
                        ebCooldown = true
                        local dir = localPlayer.Character.HumanoidRootPart.Velocity
                        for i = 1, 5 do
                            wait()
                            localPlayer.Character.HumanoidRootPart.Velocity = (Vector3.new(1.2, 0, 1.2) * dir) - Vector3.new(0, 15, 0)
                        end
                        wait()
                        localPlayer.Character.HumanoidRootPart.Velocity *= Vector3.new(1.8, 1, 1.8)
                        spawn(function()
                            wait(0.075)
                            ebCooldown = false
                        end)
                    end
                end
            end
            game:GetService("RunService").Heartbeat:Connect(edgeBugLogic)
        end
    end
})



------------------------------------ MISC (WIP) -----------------------------------

local GameSection = MiscTab:CreateSection({
    Name = "Game",
    Side = "Right"
})

local DrawingSection = MiscTab:CreateSection({
    Name = "Drawing",
    Side = "Right"
})

local WorldSection = MiscTab:CreateSection({
    Name = "World",
    Side = "Left"
})

local ConfiggSection = MiscTab:CreateSection({
    Name = "Config",
    Side = "Left"
})


GameSection:AddButton({
    Name = "Rejoin",
    Callback = function(value)
        rejoinGame()
    end
})

GameSection:AddButton({
    Name = "Copy Job ID",
    Flag = "Game_CopyJobIdButton",
    Callback = function()
        copyJobID() 
    end
})

DrawingSection:AddToggle({
    Name = "Drawing Enabled",
    Flag = "drawing_enabled", 
    Value = flags.drawing_enabled,
    Callback = function(newValue)
        flags.drawing_enabled = newValue

        if flags.drawing_enabled then
            StartDrawing()  
        else
            StopDrawing()  
        end
    end
})


DrawingSection:AddToggle({
    Name = "Velocity Graph",  
    Flag = "velo_graph",  
    Value = flags.velo_graph,  
    Callback = function(newValue)
        flags.velo_graph = newValue
    end
})

DrawingSection:AddToggle({
    Name = "Velocity Indicator", 
    Flag = "velo_indicator",
    Value = flags.velo_indicator,
    Callback = function(newValue)
        flags.velo_indicator = newValue
    end
})

DrawingSection:AddToggle({
    Name = "WASD Indicator", 
    Flag = "wasd_indicator",
    Value = flags.wasd_indicator, 
    Callback = function(newValue)
        flags.wasd_indicator = newValue
    end
})

DrawingSection:AddSlider({
    Name = "Graph Width", 
    Min = 1,  
    Max = 5, 
    Default = flags.graph_width,
    Flag = "graph_width", 
    Callback = function(newValue)
        flags.graph_width = newValue
    end
})

WorldSection:AddToggle({
    Name = "Ambience", 
    Flag = "ambience", 
    Value = flags.ambience, 
    Callback = function(newValue)
        flags.ambience = newValue
        updateAmbienceColors() 
    end,
    Parent = horizontalLayoutFrame
})


WorldSection:AddToggle({
    Name = "Skybox Changer",
    Flag = "Visuals_EnableSkyboxChanger",
    Value = false, 
    Callback = function(value)
        SkyboxToggleActive = value
        if value then
            local sky = game.Lighting:FindFirstChildOfClass("Sky")
            if sky then
                OriginalSkybox = {
                    SkyboxBk = "rbxassetid://153695414",
                    SkyboxDn = "rbxassetid://153695352",
                    SkyboxFt = "rbxassetid://153695452",
                    SkyboxLf = "rbxassetid://153695320",
                    SkyboxRt = "rbxassetid://153695383",
                    SkyboxUp = "rbxassetid://153695471"
                }
            end

            library.Notify({
                Text = "Skybox changer enabled."
            })
        else
            if OriginalSkybox then
                local sky = game.Lighting:FindFirstChildOfClass("Sky")
                if sky then
                    sky.SkyboxBk = OriginalSkybox.SkyboxBk
                    sky.SkyboxDn = OriginalSkybox.SkyboxDn
                    sky.SkyboxFt = OriginalSkybox.SkyboxFt
                    sky.SkyboxLf = OriginalSkybox.SkyboxLf
                    sky.SkyboxRt = OriginalSkybox.SkyboxRt
                    sky.SkyboxUp = OriginalSkybox.SkyboxUp
                end
            end

            library.Notify({
                Text = "Skybox changer disabled, reverted to original skybox."
            })
        end
    end
})

WorldSection:AddDropdown({
    Name = "Select Skybox", 
    Flag = "Visuals_AstralisSkybox", 
    Value = SkyboxesTable[1], 
    List = SkyboxesTable, 
    Callback = function(newValue, lastValue)
        library.Notify({
          Text = "Selected Skybox: " .. tostring(newValue),
         })
        if not SkyboxToggleActive then
            return
        end
        local formattedValue = newValue:match("^%l") and newValue:sub(1, 1):upper() .. newValue:sub(2) or newValue
        local SelectedSkybox = SkyboxesPresets[formattedValue]
        if SelectedSkybox then
            local sky = game.Lighting:FindFirstChildOfClass("Sky")
            if not sky then
                sky = Instance.new("Sky")
                sky.Parent = game.Lighting
            end

            sky.SkyboxBk = SelectedSkybox.SkyboxBk
            sky.SkyboxDn = SelectedSkybox.SkyboxDn
            sky.SkyboxFt = SelectedSkybox.SkyboxFt
            sky.SkyboxLf = SelectedSkybox.SkyboxLf
            sky.SkyboxRt = SelectedSkybox.SkyboxRt
            sky.SkyboxUp = SelectedSkybox.SkyboxUp
            library.Notify({
                Text = "Skybox theme applied: " .. newValue,
            })
        else
            print("Error: Skybox preset not found for: " .. tostring(newValue))

            library.Notify({
                Text = "Invalid skybox selection: " .. tostring(newValue),
            })
        end
    end
})


ConfiggSection:AddColorpicker({
    Name = "Indoor Ambience Color", 
    Flag = "Indoor_ambience_color", 
    Value = library.colors.Indoor_ambience_color, 
    Callback = function(newColor)
        flags.Indoor_ambience_color = newColor  
        updateAmbienceColors()  
    end,
    Parent = horizontalLayoutFrame
})

ConfiggSection:AddColorpicker({
    Name = "Outdoor Ambience Color", 
    Flag = "Outdoor_ambience_color", 
    Value = library.colors.Outdoor_ambience_color, 
    Callback = function(newColor)
        flags.Outdoor_ambience_color = newColor  
        updateAmbienceColors()  
    end,
    Parent = horizontalLayoutFrame
})

------------------------------------ SKINS -----------------------------------

local KnivesSection = SkinsTab:CreateSection({
    Name = "Knife Changer",
    Side = "Left"
})

local GlovesSection = SkinsTab:CreateSection({
    Name = "Glove Changer",
    Side = "Left"
})

local SkinsSection = SkinsTab:CreateSection({
    Name = "Skin Changer",
    Side = "Right"
})

KnivesSection:AddToggle({
    Name = "Knife Changer"
})

KnivesSection:AddDropdown({
    Name = "Knives",
    List = KnivesTable
})


GlovesSection:AddToggle({
    Name = "Glove Change"
})

GlovesSection:AddDropdown({
    Name = "Gloves",
    List = GlovesTable
})


SkinsSection:AddToggle({
    Name = "Skin Changer"
})

SkinsSection:AddDropdown({
    Name = "Skins",
    List = SkinsTable
})


------------------------------------ LUA -----------------------------------

local LuaSection = LuaTab:CreateSection({
    Name = "Lua Execution"
    Side = "Left"
})
local LuaSection2 = LuaTab:CreateSection({
    Name = "Built-in"
    Side = "Right"
})

local dropdown = LuaSection:AddDropdown({
    Name = "Select Lua",
    List = getLuaAndTxtFiles(directoryPath),
    Callback = function(fileName)
        selectedFile = directoryPath .. "\\" .. fileName
        library.Notify({
            Text = "Selected: " .. fileName,
            Duration = 5 
        })
    end
})

LuaSection:AddButton({
    Name = "Load Script",
    Callback = function()
        if selectedFile then
            local success, err = pcall(function()
                local scriptContent = readfile(selectedFile) 
                loadstring(scriptContent)() 
                library.Notify({
                    Text = "Loaded: " .. fileName,
                    Duration = 5  
                })
            end)
            if not success then
                warn("Failed to load script: " .. err)
            end
        else
            library.Notify({
                Text = "No file selected.",
                Duration = 5 
            })
        end
    end
})

LuaSection:AddButton({
    Name = "Refresh List",
    Callback = function()
        local newList = getLuaAndTxtFiles(directoryPath)
        if newList and #newList > 0 then
            if dropdown and dropdown.UpdateList then
                dropdown:UpdateList(newList) 
                library.Notify({
                    Text = "Dropdown list refreshed.",
                    Duration = 5  
                })
            else
                dropdown.List = newList
                library.Notify({
                    Text = "Manually updated dropdown list.",
                    Duration = 5 
                })
            end
        else
            library.Notify({
                Text = "No files found in the directory or unable to read the directory.",
                Duration = 5
            })
        end
    end
})

LuaSection2:AddButton('Unlock All Skins', function() 
    loadstring(game:HttpGet("https://pastebin.com/raw/Qu9inv8N", true))() 
end)

LuaSection2:AddButton('Funswapper', function() 
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Funswapper/Funswapper-Script/refs/heads/main/Variants/V1.lua", true))()
end)

------------------------------------ NOTIFY -----------------------------------

library.Notify({
    Text = "Astralis UI Loaded! - Private (Beta)",
    Duration = 5 
})


