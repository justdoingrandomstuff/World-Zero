if not game:IsLoaded() then game.Loaded:Wait() end

-- || CHECK IF IN WORLD ZERO ||
if tostring(game.GameId) ~= "985731078" then -- set to string or obfuscation can mess it up
    game:Shutdown()
end

local ScriptLoadingStart = os.clock()
-- || CHECK STEP || - turn on to see scripts loading progress
do
    local TrackProgress = false
    if TrackProgress then
        task.spawn(function()
            repeat
                print(_G.ScriptStep)
                task.wait(1)
            until _G.ScriptStep == "end"
            print("loaded everything")
        end)
    end
end

local GlobalCount = 0
local function SetGlobal(Text)
    if GlobalCount == 5 then
        task.wait()
    end

    _G.ScriptStep = Text
    GlobalCount += 1
end

-- || CREATE GUI ELEMENTS ||
local function MakeGuiElement(Type, ...)
    local NewUI = Instance.new(Type)
    local GuiTable = ...
    for Element, Data in GuiTable do
        NewUI[Element] = Data
    end
    return NewUI
end

-- || CREATE GUI FOR SCRIPT ERRORS ||
SetGlobal("error gui")
local EF = {}
local function MakeErrorGui(MessageTitle, Message, Extra)

    if not Extra or Extra == "" or Extra == "nil" then
        Extra = "Extra: <font color='#ff3333'>no extra info</font>"
    else
        Extra = string.format("Extra: <font color='#ff3333'>%*</font>", Extra)
    end

  local obj1 = Instance.new("ScreenGui")
    obj1.IgnoreGuiInset = true
    obj1.Name = "Script_Error"
    obj1.Parent = EF.HideGui() or game:GetService("CoreGui")

    local obj2 = Instance.new("Frame")
        obj2.Size = UDim2.new(1, 0, 1, 0)
        obj2.BackgroundTransparency = 1
        obj2.Position = UDim2.new(0.5, 0, 0.5, 0)
        obj2.Name = "Script_Error"
        obj2.AnchorPoint = Vector2.new(0.5, 0.5)
        obj2.Parent = obj1

        local obj3 = Instance.new("Frame")
            obj3.BackgroundColor3 = Color3.fromHex("e2e2ff")
            obj3.Size = UDim2.new(0.459500968, 0, 0.488323361, 0)
            obj3.Position = UDim2.new(0.5, 0, 0.5, 0)
            obj3.Name = "Error_Frame"
            obj3.AnchorPoint = Vector2.new(0.5, 0.5)
            obj3.Parent = obj2

            local obj4 = Instance.new("UICorner")
                obj4.Name = "UICorner"
                obj4.CornerRadius = UDim.new(0.0500000007, 0)
                obj4.Parent = obj3

            local obj5 = Instance.new("TextLabel")
                obj5.TextWrapped = true
                obj5.Size = UDim2.new(0.421533257, 0, 0.112499997, 0)
                obj5.BackgroundTransparency = 1
                obj5.Position = UDim2.new(0.0144872097, 0, 0.0152609488, 0)
                obj5.Name = "Error_Occurred"
                obj5.TextScaled = true
                obj5.FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json", Enum.FontWeight.Regular, Enum.FontStyle.Normal)
                obj5.Text = "A script error has occurred"
                obj5.TextSize = 37
                obj5.Parent = obj3

            local obj6 = Instance.new("ImageButton")
                obj6.BackgroundColor3 = Color3.fromHex("5650f6")
                obj6.Image = ""
                obj6.Size = UDim2.new(0.25, 0, 0.150000006, 0)
                obj6.Position = UDim2.new(0.739221275, 0, 0.828954279, 0)
                obj6.Name = "Join_Button"
                obj6.Selectable = true
                obj6.Parent = obj3

                local obj7 = Instance.new("UICorner")
                    obj7.Name = "UICorner"
                    obj7.CornerRadius = UDim.new(0.25, 0)
                    obj7.Parent = obj6

                local obj8 = Instance.new("TextLabel")
                    obj8.TextWrapped = true
                    obj8.Size = UDim2.new(1, 0, 1, 0)
                    obj8.BackgroundTransparency = 1
                    obj8.Position = UDim2.new(0.5, 0, 0.5, 0)
                    obj8.RichText = true
                    obj8.Name = "Join"
                    obj8.TextScaled = true
                    obj8.FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json", Enum.FontWeight.Regular, Enum.FontStyle.Normal)
                    obj8.AnchorPoint = Vector2.new(0.5, 0.5)
                    obj8.TextColor3 = Color3.fromHex("e2e2e2")
                    obj8.Text = "Join discord"
                    obj8.TextSize = 35
                    obj8.Parent = obj6

                local obj9 = Instance.new("UIPadding")
                    obj9.PaddingTop = UDim.new(0.174999997, 0)
                    obj9.PaddingLeft = UDim.new(0.150000006, 0)
                    obj9.Name = "UIPadding"
                    obj9.PaddingBottom = UDim.new(0.174999997, 0)
                    obj9.PaddingRight = UDim.new(0.150000006, 0)
                    obj9.Parent = obj6

            local obj10 = Instance.new("ImageButton")
                obj10.BackgroundColor3 = Color3.fromHex("919191")
                obj10.Image = ""
                obj10.Size = UDim2.new(0.25, 0, 0.150000006, 0)
                obj10.BackgroundTransparency = 0.75
                obj10.Position = UDim2.new(0.466563225, 0, 0.828954279, 0)
                obj10.Name = "Close_Button"
                obj10.Selectable = true
                obj10.ImageColor3 = Color3.fromHex("ff3333")
                obj10.Parent = obj3

                local obj11 = Instance.new("UICorner")
                    obj11.Name = "UICorner"
                    obj11.CornerRadius = UDim.new(0.25, 0)
                    obj11.Parent = obj10

                local obj12 = Instance.new("TextLabel")
                    obj12.TextWrapped = true
                    obj12.Size = UDim2.new(1, 0, 1, 0)
                    obj12.BackgroundTransparency = 1
                    obj12.Position = UDim2.new(0.5, 0, 0.5, 0)
                    obj12.Name = "Close"
                    obj12.TextScaled = true
                    obj12.FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json", Enum.FontWeight.Regular, Enum.FontStyle.Normal)
                    obj12.AnchorPoint = Vector2.new(0.5, 0.5)
                    obj12.Text = "close"
                    obj12.TextSize = 25
                    obj12.Parent = obj10

                local obj13 = Instance.new("UIPadding")
                    obj13.PaddingTop = UDim.new(0.174999997, 0)
                    obj13.PaddingLeft = UDim.new(0.150000006, 0)
                    obj13.Name = "UIPadding"
                    obj13.PaddingBottom = UDim.new(0.174999997, 0)
                    obj13.PaddingRight = UDim.new(0.150000006, 0)
                    obj13.Parent = obj10

            local obj14 = Instance.new("Frame")
                obj14.BackgroundColor3 = Color3.fromHex("d0d0eb")
                obj14.Size = UDim2.new(0.45655039, 0, 0.114407644, 0)
                obj14.BackgroundTransparency = 0.25
                obj14.Position = UDim2.new(0.5, 0, 0.16990459, 0)
                obj14.Name = "Error_Location"
                obj14.AnchorPoint = Vector2.new(0.5, 0.5)
                obj14.Parent = obj3

                local obj15 = Instance.new("TextLabel")
                    obj15.TextWrapped = true
                    obj15.Size = UDim2.new(1.00000012, 0, 1.00000024, 0)
                    obj15.BackgroundTransparency = 1
                    obj15.Position = UDim2.new(0.50000006, 0, 0.500000119, 0)
                    obj15.RichText = true
                    obj15.Name = "Location"
                    obj15.TextScaled = true
                    obj15.FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json", Enum.FontWeight.Regular, Enum.FontStyle.Normal)
                    obj15.AnchorPoint = Vector2.new(0.5, 0.5)
                    obj15.TextColor3 = Color3.fromHex("ff3333")
                    obj15.Text = MessageTitle
                    obj15.TextSize = 35
                    obj15.Parent = obj14

                local obj16 = Instance.new("UICorner")
                    obj16.Name = "UICorner"
                    obj16.CornerRadius = UDim.new(0.200000003, 0)
                    obj16.Parent = obj14

                local obj17 = Instance.new("UIPadding")
                    obj17.PaddingTop = UDim.new(0.100000001, 0)
                    obj17.PaddingLeft = UDim.new(0.100000001, 0)
                    obj17.Name = "UIPadding"
                    obj17.PaddingBottom = UDim.new(0.100000001, 0)
                    obj17.PaddingRight = UDim.new(0.100000001, 0)
                    obj17.Parent = obj14

            local obj18 = Instance.new("Frame")
                obj18.BackgroundColor3 = Color3.fromHex("d0d0eb")
                obj18.Size = UDim2.new(0.899999857, 0, 0.566264868, 0)
                obj18.BackgroundTransparency = 0.25
                obj18.Position = UDim2.new(0.5, 0, 0.525351286, 0)
                obj18.Name = "Error_Text"
                obj18.AnchorPoint = Vector2.new(0.5, 0.5)
                obj18.Parent = obj3

                local obj19 = Instance.new("TextLabel")
                    obj19.TextWrapped = true
                    obj19.Size = UDim2.new(0.995358765, 0, 0.876286268, 0)
                    obj19.BackgroundTransparency = 1
                    obj19.Position = UDim2.new(0.502320588, 0, 0.438143224, 0)
                    obj19.RichText = true
                    obj19.Name = "Error_Main"
                    obj19.TextScaled = true
                    obj19.FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json", Enum.FontWeight.Regular, Enum.FontStyle.Normal)
                    obj19.AnchorPoint = Vector2.new(0.5, 0.5)
                    obj19.TextColor3 = Color3.fromHex("ff3333")
                    obj19.Text = Message
                    obj19.TextSize = 35
                    obj19.Parent = obj18

                local obj20 = Instance.new("UICorner")
                    obj20.Name = "UICorner"
                    obj20.CornerRadius = UDim.new(0.0500000007, 0)
                    obj20.Parent = obj18

                local obj21 = Instance.new("TextLabel")
                    obj21.TextWrapped = true
                    obj21.Size = UDim2.new(1.00000012, 0, 0.11999999, 0)
                    obj21.BackgroundTransparency = 1
                    obj21.Position = UDim2.new(0.5, 0, 0.936286449, 0)
                    obj21.RichText = true
                    obj21.Name = "Error_Extra"
                    obj21.TextScaled = true
                    obj21.FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json", Enum.FontWeight.Regular, Enum.FontStyle.Normal)
                    obj21.AnchorPoint = Vector2.new(0.5, 0.5)
                    obj21.Text = Extra
                    obj21.TextSize = 35
                    obj21.Parent = obj18

                local obj22 = Instance.new("UIPadding")
                    obj22.PaddingTop = UDim.new(0.00999999978, 0)
                    obj22.PaddingLeft = UDim.new(0.00999999978, 0)
                    obj22.Name = "UIPadding"
                    obj22.PaddingBottom = UDim.new(0.00999999978, 0)
                    obj22.PaddingRight = UDim.new(0.00999999978, 0)
                    obj22.Parent = obj18

        local obj23 = Instance.new("Frame")
            obj23.ZIndex = -1
            obj23.Size = UDim2.new(0.459500939, 0, 0.488323361, 0)
            obj23.BackgroundTransparency = 1
            obj23.Position = UDim2.new(0.5, 0, 0.5, 0)
            obj23.Name = "Gui_Glow"
            obj23.AnchorPoint = Vector2.new(0.5, 0.5)
            obj23.Parent = obj2

            local obj24 = Instance.new("ImageButton")
                obj24.ZIndex = -1
                obj24.BackgroundColor3 = Color3.fromHex("e2e2ff")
                obj24.ImageTransparency = 0.5
                obj24.Image = "rbxassetid://136878391730807"
                obj24.Size = UDim2.new(1.09508789, 0, 1.11842096, 0)
                obj24.BackgroundTransparency = 1
                obj24.Position = UDim2.new(0.5, 0, 0.5, 0)
                obj24.Name = "Glow_Image"
                obj24.Selectable = true
                obj24.ImageColor3 = Color3.fromHex("e2e2ff")
                obj24.AnchorPoint = Vector2.new(0.5, 0.5)
                obj24.Parent = obj23

	local Error_Blur = MakeGuiElement("BlurEffect", {
		Size = 50,
		Parent = game:GetService("Lighting")
	})

    pcall(function()
        if sethiddenproperty then
            sethiddenproperty(obj1, "OnTopOfCoreBlur", true)
        elseif setscriptable then
            setscriptable(obj1, "OnTopOfCoreBlur", true)
            obj1.OnTopOfCoreBlur = Enabled
            setscriptable(obj1, "OnTopOfCoreBlur", false)
        end
    end)

    local ErrorGuiDiscordButton = obj6.MouseButton1Click:Connect(function()
        if setclipboard then
            setclipboard("https://discord.gg/bNWWpqFZbP")
            game:GetService("StarterGui"):SetCore("SendNotification", {
                Title = "Copied!",
                Text = "The invite to the discord has been copied to your devices clipboard!",
                Duration = 5,
                Icon = "rbxasset://textures/ui/LuaApp/ExternalSite/discord@3x.png",
                DisplayOrder = math.huge
            })
        end
    end)

    local ErrorGuiClosed
	obj10.MouseButton1Click:Once(function()
		Error_Blur:Destroy()
        Error_Blur = nil
		obj1:Destroy()
        obj1 = nil
        ErrorGuiDiscordButton:Disconnect()
        ErrorGuiDiscordButton = nil
        ErrorGuiClosed = true
	end)

    repeat
        task.wait()
    until ErrorGuiClosed
end

-- || EXECUTOR FUNCTIONS ||
SetGlobal("getting executor references")
EF.GetExecutor = identifyexecutor or getexecutorname or nil
EF.ExecutorName, EF.ExecutorVersion, EF.ExecutorBuild = EF.GetExecutor()
EF.SendRequest = http_request or request or (EF.ExecutorName and EF.ExecutorName.request) or (EF.ExecutorName and EF.ExecutorName.http_request) or (http and http.request) or nil
EF.Hook = hookfunc or hookfunction or nil
EF.ClearHook = restorefunc or restorefunction or nil
EF.Queue = queue_on_teleport or queueonteleport or queue_on_tp or queueontp or queueteleport or nil
EF.ClearQueue = clear_teleport_queue or clearqueueonteleport or clearteleportqueue or clear_tp_queue or cleartpqueue or clear_queue_on_teleport or nil
EF.RaknetFunction = rnet or raknet or RakNet or nil
EF.Desync = (EF.RaknetFunction and EF.RaknetFunction.desync) or nil
EF.HideGui = get_hidden_gui or gethui or gethiddengui or get_hidden_ui or gethiddenui or nil
EF.NewClosure = newcclosure or nil
EF.CloneRef = cloneref or clonereference or nil
EF.CheckHook = ishooked or isfunctionhooked or is_hooked or is_function_hooked or nil
EF.ASDFG = gethwid or get_hwid or get_device_id or getsystemid or "unknown"

-- || RETURN SERVICE ||
SetGlobal("return things for the script")
local function ReturnService(Service)
    local ReturnService = game:GetService(Service)
    if ReturnService then
        return EF.CloneRef(ReturnService)
    else
        warn("Unable to get service", Service)
    end
end

-- || RETURN ATTRIBUTE ||
local function WaitForAttribute(Parent, Attribute)
    repeat task.wait() until Parent:GetAttribute(Attribute)
    return Parent:GetAttribute(Attribute)
end

-- || ROBLOX SERVICES ||
SetGlobal("getting Service paths")
local Workspace = ReturnService("Workspace")
local Players = ReturnService("Players")
local CoreGui = ReturnService("CoreGui")
local StarterGui = ReturnService("StarterGui")
local ReplicatedStorage = ReturnService("ReplicatedStorage")
local HttpService = ReturnService("HttpService")
local VirtualUser = ReturnService("VirtualUser")
local RunService = ReturnService("RunService")
local MarketplaceService = ReturnService("MarketplaceService")
local TeleportService = ReturnService("TeleportService")
local TweenService = ReturnService("TweenService")

-- || RETURN CHILD ||
SetGlobal("getting ReplicatedStorage paths")
local function ReturnChild(Parent, Child)
    return EF.CloneRef(Parent:WaitForChild(Child, math.huge))
end

local Shared = ReturnChild(ReplicatedStorage, "Shared")
local SharedAssets = ReturnChild(ReplicatedStorage, "SharedAssets")
local Remotes = ReturnChild(ReplicatedStorage, "Remotes")
local Client = ReturnChild(ReplicatedStorage, "Client")

-- || GAME SCRIPTS ||
SetGlobal("getting ReplicatedStorage child paths")
local function GetShared(Script)
    return EF.CloneRef(Shared:WaitForChild(Script, math.huge))
end

local function GetSharedAsset(Script)
    return EF.CloneRef(SharedAssets:WaitForChild(Script, math.huge))
end
local Battlepass = GetShared("Battlepass")
local Charms = GetShared("Charms")
local Chests = GetShared("Chests")
local Drops = GetShared("Drops")
local Effects = GetShared("Effects")
local Health = GetShared("Health")
local Inventory = GetShared("Inventory")
local Items = GetShared("Items")
local Missions = GetShared("Missions")
local SMobs = GetShared("Mobs")
local ModelProvider = GetShared("ModelProvider")
local Party = GetShared("Party")
local Pets = GetShared("Pets")
local Quests = GetShared("Quests")
local Shop = GetSharedAsset("Shop")
local Skills = GetShared("Skills")
local Teleport = GetShared("Teleport")
local WalkspeedManager = GetShared("WalkspeedManager")

-- || GAME VARIABLES ||
SetGlobal("getting Workspace child paths")
local Camera = ReturnChild(Workspace, "Camera")
local Mobs = ReturnChild(Workspace, "Mobs")
local MissionObjects

-- || SCRIPT VARIABLES ||
SetGlobal("setting up script dependencies")
local Library
local SaveManager
local Options
local Toggles
local ScriptUnloaded
local SV = {}
SV.Drops = {}
local ISV = {}
ISV.MobTable = {}
local ConnectionTable = {}
local AvoidMobs = {}
local TeleportParts = {}
local StatTotals = {}
local AntiCheatNumber = 67
local Class
local ClassSkills
local PetSkills
local LocalPlayer = Players.LocalPlayer
local PlayerName = LocalPlayer.Name
local PlayerID = LocalPlayer.UserId
local PlayerGui = ReturnChild(LocalPlayer, "PlayerGui")
local PlayerPing = 0
local PlayerProfile
local ProfileInventory
local PlayerCharacter
local PlayerCollider
local PlayerRoot
local AddedDelay = 0
local Xdistance = 0
local Ydistance = 0
local TempStop
local HoldForRealTime
local RestartAtFloor = 200
local CurrentMob
local IsMobCamera
local KillSwitch
local KeepTier = 5
local SellItemCheck = 0
local OffsetMax = 0
local EquipInProgress = 0
local MobRotationSpeed = 20
local DelayPetAttacks
local IsAliveMobs = 0
local DiscordPingType = "@everyone"
local TeleportMob
local StuckDelay = 60
local DelayAttacks
local IsBoss
local EventOverride
local CanTarget = true
local PingMultiplier = 1
local PlayerStandPart = nil
local StandPartHeight = nil

do
    ConnectionTable["ConnectNewCharacter"] = LocalPlayer.CharacterAdded:Connect(function(NewCharacter)
        PlayerCharacter = NewCharacter
        PlayerRoot = NewCharacter:WaitForChild("HumanoidRootPart", math.huge)
        PlayerCollider = NewCharacter:WaitForChild("Collider", math.huge)
    end)
    if LocalPlayer.Character then
        PlayerCharacter = LocalPlayer.Character
    end
    if PlayerCharacter and PlayerCharacter:FindFirstChild("HumanoidRootPart") then
        PlayerRoot = PlayerCharacter.HumanoidRootPart
    end
    if PlayerCharacter and PlayerCharacter:FindFirstChild("Collider") then
        PlayerCollider = PlayerCharacter.Collider
    end
end

SetGlobal("setting up auto execute")
if EF.Queue then
    local FileName = "JDRS/AutoExecute"
    if isfile(FileName) then
        EF.Queue([[loadstring(game:HttpGet("https://raw.githubusercontent.com/justdoingrandomstuff/World-Zero/main/autofarm"))()]])
        SV.AlreadyQueued = true
    end
end

SetGlobal("identify bad executor")
if (EF.ExecutorName == "Xeno" or EF.ExecutorName == "Solara" or EF.ExecutorName == "Velocity") then
    SV.BadExecutor = true
end

SetGlobal("checking for tabs to skip loading")
do
    local FileName = "JDRS/SkipTabs"
    if isfile(FileName) and isfile("JDRS/saved_configs/settings/autoload.txt") then
        for Index, Tab in pairs(HttpService:JSONDecode(readfile(FileName))) do
            SV[Tab] = true
        end
    end
end

-- || IDENTIFY LOCATION ||
SetGlobal("setting up location identifier")
local StringPlaceID = tostring(game.PlaceId)
local IsWorld = false
local IsMainMenu = false
local IsDungeon = false
local IsTower = false

local Locations = {
    MainMenu = {
        ["2727067538"] = true -- main menu
    },
    WorldHubs = {
        ["4310463616"] = true, -- world 1
        ["4310463940"] = true, -- world 2
        ["4465987684"] = true, -- world 3
        ["4646472003"] = true, -- world 4
        ["5703355191"] = true, -- world 5
        ["6075083204"] = true, -- world 6
        ["6847035264"] = true, -- world 7
        ["9944262922"] = true, -- world 8
        ["10651517727"] = true, -- world 9
        ["14914684761"] = true, -- world 10
        ["7499964980"] = true, -- market
        ["6510868181"] = true, -- pvp
        ["139316833473171"] = true, -- guild hub
        ["105045973347410"] = true, -- guild hall
        ["87656507991995"] = true, -- valentines hub
        ["100868012981049"] = true, -- easter hub
        ["18567064955"] = true, -- vane hub
        ["125645867930579"] = true, -- kraken hub
        ["5862275930"] = true, -- halloween hub
        ["4526768266"] = true, -- holiday hub
        ["111346137875750 "] = true, -- market house
        ["73832225581864"] = true, -- w1 house
        ["84106607802351"] = true, -- w2 house
        ["136326194224398"] = true, -- w3 house
        ["73334696605120"] = true, -- w7 house
        ["104886402902960"] = true -- og world 1
    },
    Dungeons = {
        ["107701891477606"] = 49, -- 1-1 tutorial
        ["83712338696299"] = 54, -- chad tutorial
        ["2978696440"] = 1, -- 1-1
        ["4310476380"] = 3, -- 1-2
        ["4310464656"] = 2, -- 1-3
        ["4310478830"] = 4, -- 1-4
        ["3383444582"] = 6, -- 1-5
        ["3885726701"] = 11, -- 2-1
        ["3994953548"] = 12, -- 2-2
        ["4050468028"] = 13, -- 2-3
        ["3165900886"] = 7, -- 2-4
        ["4465988196"] = 14, -- 3-1
        ["4465989351"] = 15, -- 3-2
        ["4465989998"] = 16, -- 3-3
        ["4646473427"] = 20, -- 4-1
        ["4646475342"] = 19, -- 4-2
        ["4646475570"] = 18, -- 4-3
        ["6386112652"] = 24, -- 5-1
        ["11466514043"] = 35, -- 5-2
        ["6510862058"] = 25, -- 6-1
        ["11533444995"] = 36, -- 6-2
        ["6847034886"] = 26,  -- 7-1
        ["11644048314"] = 37, -- 7-2
        ["9944263348"] = 30, -- 8-1
        ["10014664329"] = 31, -- 8-2
        ["10651527284"] = 32, -- 9-1
        ["10727165164"] = 33, -- 9-2
        ["14914700740"] = 41, -- 10-1
        ["14914855930"] = 42, -- 10-2
        ["128961185668563"] = 53 -- heavenly raid
    },
    EventDungeons = {
        ["93889085342251"] = 51, -- graffiti beach
        ["102111805987017"] = 47, -- hunt 2025
        ["81373988789544"] = 46, -- cupid arena
        ["109614960834199"] = 50, -- alien invasion arena
        ["138178936582742"] = 48, -- zero arena
        ["110769392907898"] = 52, -- easter arena
        ["75540798045662"] = 45, -- kraken arena
        ["18567068844"] = 44, -- vane arena
        ["5862277651"] = 22, -- fallen anrea
        ["4526768588"] = 17 -- klaus arena
    },
    Towers = {
        ["5703353651"] = 21, -- tower 1
        ["6075085184"] = 23, -- tower 2
        ["7071564842"] = 27, -- tower 3
        ["10089970465"] = 29, -- tower 4
        ["10795158121"] = 34, -- tower 5
        ["15121292578"] = 43, -- tower 6
        ["14400549310"] = 39, -- celestial tower
        ["13988110964"] = 38 -- infinite tower
        --["130171241672058"] = 56 -- og tower
    }
}
if Locations.MainMenu[StringPlaceID] then
    IsMainMenu = true
    print("JDRS: player in main menu")
elseif Locations.WorldHubs[StringPlaceID] then
    IsWorld = true
    print("JDRS: player in lobby")
elseif Locations.Dungeons[StringPlaceID] then
    IsDungeon = true
    print("JDRS: player in dungeon")
elseif Locations.Towers[StringPlaceID] then
    IsDungeon = true
    IsTower = true
    print("JDRS: player in tower")
elseif Locations.EventDungeons[StringPlaceID] then
    IsEventDungeon = true
    IsDungeon = true
    print("JDRS: player is in event dungeon")
else
    IsWorld = true
    print("JDRS: cannot determine where player is located... placeid: " ..StringPlaceID)
end

-- || FIND CURRENT DUNGEON AND DELETE TABLE ||
if not (IsWorld or IsMainMenu) then
    ISV.CurrentDungeonID = Locations.EventDungeons[StringPlaceID] or Locations.Dungeons[StringPlaceID] or Locations.Towers[StringPlaceID] or nil
end
Locations = nil

SetGlobal("request message")
local function RequestMessage(WebsiteLink, MessageContent, HighRiskRequest)
    if not WebsiteLink and not HighRiskRequest then
        warn("No webhook link provided")
        return
    end
        if not EF.SendRequest then
            return
        end
        EF.SendRequest({
            Url = WebsiteLink,
            Method = "POST",
            Headers = {
                ["Content-Type"] = "application/json"
            },
            Body = HttpService:JSONEncode(MessageContent)
        })
    end)
end

SetGlobal("save error to file")
local function SaveErrorToFile(ErrorLocation, ErrorMessage, ExtraInfo)
    if ISV.TeleportingToAnotherServer then
        return
    end
    ErrorLocation = tostring(ErrorLocation)
    ErrorMessage = tostring(ErrorMessage)
    ExtraInfo = tostring(ExtraInfo)
    local ErrorFileName = "JDRS_script_error.txt"
    appendfile(ErrorFileName, string.format(
        "Error: %*\nLocation: %*Extra info: %*\nDate: %*\n\n",
        ErrorMessage, ErrorLocation, ExtraInfo, os.date()
    ))
    MakeErrorGui(ErrorLocation, ErrorMessage, ExtraInfo, nil)
end

SetGlobal("identifying executor")
do
    local Success, Result = pcall(function()
        print("JDRS: player is using", EF.ExecutorName, EF.ExecutorVersion)
    end)
    if not Success then
        if not EF.GetExecutor then
            print("JDRS: couldn't identify executor, identity function missing.")
        else
            print("JDRS: couldn't identify executor,", Result)
        end
    end
end

SetGlobal("setting up ignore file download dates")
do
    local Success, Result = pcall(function()
        local FileName = "JDRS/ignore/DD"
        if not isfile(FileName) then
            writefile(FileName, HttpService:JSONEncode(
                {
                    P = { T = os.clock(), V = 0 },
                    L = { T = os.clock(), V = 0 },
                    C = { T = os.clock(), V = 0 },
                    S = { T = os.clock(), V = 0 }
                }
            ))
        end
    end)
    if not Success then
        SaveErrorToFile("FILE DATA", Result)
    end
end

SetGlobal("save script to files")
local function SaveScriptToFiles(Link, File, Version, DeleteFile)
    local FileData
    local Success, Result = pcall(function()
        if isfile and writefile and readfile then
            local DownloadDates = HttpService:JSONDecode(readfile("JDRS/ignore/DD"))
            local FileName = "JDRS/ignore/" ..File
            if DeleteFile and isfile(FileName) then
                delfile(FileName)
            end

            if not isfile(FileName) then
                repeat
                    local Downloaded, DownloadError = pcall(function()
                        writefile(FileName, game:HttpGet(Link))
                    end)
                    if not DownloadError then
                        DownloadDates[File].T = os.time()+86400
                        DownloadDates[File].V = Version
                        writefile("JDRS/ignore/DD", HttpService:JSONEncode(DownloadDates))
                        break
                    end
                    warn("writefile() failed or data was corrupted, trying again in 2 seconds\nReason: " ..tostring(DownloadError))
                    task.wait(2)
                until ScriptUnloaded or KillSwitch
            end

            if isfile(FileName) then
                local FileReference = DownloadDates[File]
                if FileReference.T > os.time() and FileReference.V == Version then
                    local Downloaded, DownloadError = pcall(function()
                        FileData = loadstring(readfile(FileName))()
                    end)
                    if not FileData or (FileData and (FileData == "")) then
                        warn("failed to read file, possibly corrupted. Redownloading\nReason: " ..tostring(DownloadError))
                        FileData = SaveScriptToFiles(Link, File, Version, true)
                    end
                else
                    FileData = SaveScriptToFiles(Link, File, Version, true)
                end
            end
        else
            FileData = loadstring(game:HttpGet(Link))()
        end
    end)
    if not Success then
        SaveErrorToFile("FILE MANAGER", Result, File)
    end
    task.wait()
    return FileData
end

SetGlobal("creating script tables")
SV.DungeonPartList = {
    { "MissionStart", DescendantCheck = true },
    DeleteParts = {
        { "MissionObjects", "DamageDroppers" }, { "TeleportSystem", MultipleExists = true }, { "MissionObjects", "FallAreas" }
    }
}
SV.WheelItems = {
    "WebbedWings", "WispLantern", "CrowKing", "CrowQueen", "CastingShadow",
    "AstralHorns", "DreamCatcherHalo", "SpiderCrown"
}
SV.SpecialHexColors = {
	"ffffff", "000000", "e6e6e6", "1e1e1e", "d4af37",
    "ff1337", "11ccee", "ffaabb", "ddeadd", "dec0de",
    "b00000", "bbaadd", "c0aa11", "00bdae", "55eeaa",
    "ffaded", "beeeee", "ffaaee", "ac11dd", "acce55",
    "ff0011", "decade", "deeeed", "deeee1", "b1a2ed",
    "aaaaaa"
}
SV.EggList = {
    'StarEgg', 'JungleEgg', 'CrystalEgg', 'ChristmasEgg', 'DesertEgg',
    'MoltenEgg', 'OceanEgg', 'SkyEgg', 'CatEgg', 'CatEggHalloween',
    'AlligatorEgg', 'FairyEgg', 'AetherEgg', 'CabbageEgg', 'SkeletonEgg',
    'CupidEgg', 'SlimeEgg', 'TeddyEgg', 'SantaEgg', 'ArcaneEgg',
    'GhostEgg', 'PenguinEgg', 'RobloxEventEggHatchable', 'GoldenEgg', 'MiseryEgg',
    'BunnyEgg', 'RheaEgg', "SuperCrystalEgg", "SuperDesertEgg", "SuperFairyEgg",
    "SuperStarEgg", "SuperMoltenEgg", "VoidEgg", "SuperArcaneEgg", "EasterPetEgg",
    "SuperSkyEgg", "SuperAlligatorEgg", "SuperOceanEgg", "SuperJungleEgg"
}
SV.TowerEggList = {
    ["MoltenEgg"] = true,
    ["OceanEgg"] = true,
    ["SkyEgg"] = true,
    ["AlligatorEgg"] = true,
    ["FairyEgg"] = true,
    ["ArcaneEgg"] = true
}
SV.DungeonListTable = {
    { Level = 175, DungeonName = "Nightmare Portal", DungeonDelay = 60, DungeonID = 1005 },
    { Level = 135, DungeonName = "Astral Academy", DungeonDelay = 135, DungeonID = 42, SpecialPerk = true },
    { Level = 130, DungeonName = "Crystal Chaos", DungeonDelay = 115, DungeonID = 41, SpecialPerk = true },
    { Level = 120, DungeonName = "Aether Fortress", DungeonDelay = 45, DungeonID = 33 },
    { Level = 115, DungeonName = "Treetop Trouble", DungeonDelay = 90, DungeonID = 32 },
    { Level = 105, DungeonName = "Ruin Rush", DungeonDelay = 65, DungeonID = 31, SpecialPerk = true },
    { Level = 100, DungeonName = "Rescue in the Ruins", DungeonDelay = 78, DungeonID = 30, SpecialPerk = true },
    { Level = 95, DungeonName = "The Labyrinth", DungeonDelay = 20, DungeonID = 37 },
    { Level = 90, DungeonName = "The Underworld", DungeonDelay = 85, DungeonID = 26 },
    { Level = 80, DungeonName = "Treasure Hunt", DungeonDelay = 36, DungeonID = 36, SpecialPerk = true },
    { Level = 75, DungeonName = "Rough Waters", DungeonDelay = 55, DungeonID = 25, SpecialPerk = true },
    { Level = 65, DungeonName = "Konoh Inferno", DungeonDelay = 40, DungeonID = 35 },
    { Level = 60, DungeonName = "Konoh Heartlands", DungeonDelay = 45, DungeonID = 24 },
    { Level = 55, DungeonName = "Pyramid Dungeon", DungeonDelay = 40, DungeonID = 18 },
    { Level = 50, DungeonName = "Deserted Burrowmine", DungeonDelay = 40, DungeonID = 19 },
    { Level = 45, DungeonName = "Scrap Canyon", DungeonDelay = 50, DungeonID = 20 },
    { Level = 40, DungeonName = "Winter Dungeon", DungeonDelay = 60, DungeonID = 16, SpecialPerk = true },
    { Level = 35, DungeonName = "Winter Cavern", DungeonDelay = 20, DungeonID = 15, SpecialPerk = true },
    { Level = 30, DungeonName = "Mountain Pass", DungeonDelay = 35, DungeonID = 14, SpecialPerk = true },
    { Level = 26, DungeonName = "Volcano Dungeon", DungeonDelay = 40, DungeonID = 7, SpecialPerk = true },
    { Level = 22, DungeonName = "Volcano's Shadow", DungeonDelay = 59, DungeonID = 13, SpecialPerk = true },
    { Level = 18, DungeonName = "Mama Trauma", DungeonDelay = 35, DungeonID = 12, SpecialPerk = true },
    { Level = 15, DungeonName = "Temble of Ruin", DungeonDelay = 33, DungeonID = 11, SpecialPerk = true },
    { Level = 12, DungeonName = "Gravetower Dungeon", DungeonDelay = 45, DungeonID = 6 },
    { Level = 10, DungeonName = "Kingslayer", DungeonDelay = 32, DungeonID = 4 },
    { Level = 7, DungeonName = "Dire Problem", DungeonDelay = 15, DungeonID = 2 },
    { Level = 4, DungeonName = "Scarecrow Defense", DungeonDelay = 20, DungeonID = 3 },
    { Level = 1, DungeonName = "Crabby Crusade", DungeonDelay = 20, DungeonID = 1 },
    { Level = 0, DungeonName = "Celestial Tower", DungeonDelay = 580, DungeonID = 39 },
    { Level = 0, DungeonName = "Arcane Tower", DungeonDelay = 320, DungeonID = 43 },
    { Level = 0, DungeonName = "Aether Tower", DungeonDelay = 270, DungeonID = 34 },
    { Level = 0, DungeonName = "Oasis Tower", DungeonDelay = 280, DungeonID = 29 },
    { Level = 0, DungeonName = "Mezuvian Tower", DungeonDelay = 270, DungeonID = 27 },
    { Level = 0, DungeonName = "Atlantis Tower", DungeonDelay = 279, DungeonID = 23 },
    { Level = 0, DungeonName = "Prison Tower", DungeonDelay = 240, DungeonID = 21 },
    { Level = 0, DungeonName = "Infinite Tower", DungeonDelay = 0, DungeonID = 38 }
}

SetGlobal("creating script function")

SetGlobal("check for character")
local function CheckForCharacter(TimeStarted)
    if not PlayerCharacter then
        repeat task.wait() until PlayerCharacter
    end
    if not PlayerRoot then
        repeat task.wait() until PlayerRoot
    end
    if not PlayerCollider then
        repeat task.wait() until PlayerCollider
    end
    return TimeStarted
end

SetGlobal("format number")
local function FormatNumber(n)
    n = tostring(n)
    return n:reverse():gsub("...","%0,",math.floor((#n-1)/3)):reverse()
end

SetGlobal("format decimal")
local function FormatDecimal(decimal)
	return tonumber(string.format("%.2f", decimal))
end

SetGlobal("get percentage")
local function GetPercentage(initial, current)
	return (current/initial)*100
end

SetGlobal("seconds to string")
local function SecondsToString(seconds)
    local StartingSeconds = seconds
    local days = math.floor(seconds / 86400)
    local hours = math.floor(seconds % 86400 / 3600)
    local minutes = math.floor(seconds % 3600 / 60)
    seconds = math.floor(seconds % 60)
    if StartingSeconds < 60 then
        return tostring(math.floor(StartingSeconds)).. "s"
    elseif StartingSeconds < 3600 then
        return string.format("%d:%02d", minutes, seconds)
    elseif StartingSeconds < 86400 then
        return string.format("%d:%02d:%02d", hours, minutes, seconds)
    else
        return string.format("%d:%02d:%02d:%02d", days, hours, minutes, seconds)
    end
end

SetGlobal("is mission over")
local function IsMissionOver()
    return Workspace:GetAttribute("MissionCleared") or false
end

SetGlobal("check for avoid mobs")
local function CheckForAvoidMobs()
    if IsDungeon and not SV.CanRequire then
        local Success, Result = pcall(function()
            local GetPartyData = Remotes:WaitForChild("Party_GetPartyData", math.huge):InvokeServer()
            SV.PartyRaidID = GetPartyData.RaidID.Value
            if SV.PartyRaidID == 1 then AvoidMobs["BOSSDireBoarwolf"] = true; AvoidMobs["BOSSTreeEnt"] = true end -- World 1
            if SV.PartyRaidID == 20 then AvoidMobs["BOSSAnubis"] = true; AvoidMobs["BOSSHogRider"] = true end -- World 4
            if SV.PartyRaidID == 22 then AvoidMobs["BOSSFallenKing"] = true end -- The Fallen Throne
            if SV.PartyRaidID == 24 then AvoidMobs["CorruptedGreaterTree"] = true end -- World 5
            if SV.PartyRaidID == 25 then AvoidMobs["BOSSKrakenMain"] = true; AvoidMobs["DavyJones"] = true; AvoidMobs["Nautilus"] = true; AvoidMobs["PirateCrab"] = true end -- World 6
            if SV.PartyRaidID == 26 then AvoidMobs["HadesCerberus"] = true; AvoidMobs["SentryOfCerberus"] = true; AvoidMobs["MinotaurDungeonBoss"] = true end -- World 7
            if SV.PartyRaidID == 28 then AvoidMobs["BOSSEvilSanta"] = true end -- North Pole 
            if SV.PartyRaidID == 32 then AvoidMobs["RustyCommander"] = true; AvoidMobs["AetherKing"] = true end -- World 9
            if SV.PartyRaidID == 41 then AvoidMobs["MiniBossCrystalWeaver"] = true; AvoidMobs["DungeonBOSSCrystalWolf"] = true; AvoidMobs["BOSSKandrix"] = true end -- World 10
            if SV.PartyRaidID == 44 then AvoidMobs["EVENTBOSSVane"] = true; AvoidMobs["BOSSDarkriseDarkDragon"] = true end -- Vane's Lair
            if SV.PartyRaidID == 45 then AvoidMobs["EVENTBOSSKraken"] = true; AvoidMobs["EVENTBOSSDavyJones"] = true end -- The Depths
            if SV.PartyRaidID == 46 then AvoidMobs["EVENTBOSSCupid"] = true end -- Cradle of Hearts
        end)
        if not Success then
            SaveErrorToFile("BOSS MOBS", Result)
        end
    else
        AvoidMobs = nil
    end
end

SetGlobal("check player ping")
local function CheckPlayerPing()
    local Success, Result = pcall(function()
        while not KillSwitch do
            if PingMultiplier ~= 0 then
                PlayerPing = LocalPlayer:GetNetworkPing() * PingMultiplier
            else
                PlayerPing = 0
            end
            task.wait(1)
        end
    end)
    if not Success then
        SaveErrorToFile("PLAYER PING", Result)
    end
end

SetGlobal("create hook on function")
local function CreateHookOnFunction(Function, Enabled)
    if Enabled then
        EF.Hook(Function, EF.NewClosure(function()
            return
        end))
    else
        if EF.CheckHook(Function) then
            EF.ClearHook(Function)
        end
    end
end

SetGlobal("mob scanner")
local function MobScanner()
    CheckForCharacter()
    if not IsMainMenu then
        if SV.CanRequire and EF.Hook and EF.NewClosure then
            local PlayerRemover = require(SMobs:WaitForChild("PlayerRemover", math.huge))
            CreateHookOnFunction(PlayerRemover.AddMobToSearch, true)
            for Index, Mob in Mobs:GetChildren() do
                PlayerRemover:RemoveMobFromSearch(Mob)
            end
        end
    end
    if IsDungeon then
        local Success, Result = pcall(function()
            local FakeSpawnParts = {
                ["DireBridgeSpawn"] = true,
                ["DireBoulderSpawn"] = true,
                ["DireCaveSpawn"] = true,
                ["FakeKingSpawn"] = true,
                ["BridgeMama"] = true,
                ["CerberusSpawn1"] = true,
                ["CerberusSpawn2"] = true,
                ["FakeBoss"] = true,
                ["FakeBossSpawn"] = true
            }
            local FakeMobs = {
                ["Fake"] = true
            }
            local PriorityMobs = {
                ["EVENTBOSSEasterBunny"] = true,
                ["EVENTBOSSEasterBunnyEnraged"] = true,
                ["BabyWinterfall"] = true,
                ["BabyIgnis"] = true,
                ["BOSSSeraphiel"] = true
            }
            local ShrinkCollider = {
                ["CorruptedGreaterTree"] = Vector3.new(1, 1, 1),
                ["BOSSCrystalGolem"] = Vector3.new(52, 30, 52),
                ["EVENTBOSSZeroGuardian"] = Vector3.new(52, 30, 52),
                ["Crystal"] = Vector3.new(25, 20, 25),
                ["KrakenArm"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#1"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#2"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#3"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#4"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#5"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#6"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#7"] = Vector3.new(17, 25, 17),
                ["EVENTBOSSKrakenArm-Arm#8"] = Vector3.new(17, 25, 17)
            }
            local DelayBosses = {
                ["BOSSTreeEnt"] = true,
                ["HadesCerberus"] = true,
                ["EVENTBOSSEasterBunny"] = true
            }
            local DontAttackBosses = {
                ["BOSSKrakenMain"] = true,
                ["AlienMothership"] = true,
                ["AlienUFO"] = true
            }
            local Summons = {
                ["SummonerSummonWeak"] = true,
                ["SummonerSUmmonStrong"] = true,
                ["NecromancerSummon"] = true,
                ["EvilClown"] = true
            }
            local Blockers = {
                ["Pillar1"] = true, -- 1-5 blocker
                ["Pillar2"] = true, -- 1-5 blocker
                ["Pillar3"] = true, -- 1-5 blocker
                ["IceBarricade"] = true, -- 3-2 blocker
                ["Blocker1"] = true, -- 3-3 blocker
                ["Blocker2"] = true, -- 3-3 blocker
                ["Blocker3"] = true, -- 3-3 blocker
                ["Model"] = true, -- 4-1 blockers
                ["Crystal"] = true, -- tower 6 blockers
                ["EasterGiantEgg"] = true, -- easter boss blocker
                ["1"] = true, -- chad tutorial 
                ["AngelSculpture"] = true, -- heavenly boss heal
                ["SwordOfDecree"] = true, -- heavenly boss sword
                ["FallenClock"] = true -- falllen queen thing

            }
            ConnectionTable["MobInvincibilityUpdate"] = Remotes:WaitForChild("Mobs_InvincibilityUpdated", math.huge).OnClientEvent:Connect(function(Mob, Value)
                local UpdateInvincibility
                local AllocatedLoadTime = time() + 5
                repeat
                    if time() > AllocatedLoadTime then
                        break
                    end
                    UpdateInvincibility = ISV.MobTable[Mob]
                    task.wait()
                until UpdateInvincibility
                if UpdateInvincibility then
                    if Value then
                        UpdateInvincibility.Invincible = true
                    else
                        UpdateInvincibility.Invincible = false
                    end
                end
            end)
            if SV.CanRequire then
                local rMob = require(SMobs)
                local BigNumber = math.huge
                local function ValidMob(Mob, MobName)
                    local IsDebug = ISV.Debug
                    IsAliveMobs += 1
                    if Mob.Parent and Mob.Parent == Workspace.Characters then
                        if IsDebug then
                            warn("JDRS:", Mob, "(is a player)")
                        end
                        IsAliveMobs -= 1
                        return
                    end
                    if not MobName then
                        MobName = Mob.Name
                    end
                    if FakeMobs[MobName] then
                        if IsDebug then
                            warn("JDRS:", Mob, "(fake mob)")
                        end
                        IsAliveMobs -= 1
                        return
                    end
                    if Blockers[MobName] then
                        local BlockerHitbox = Mob:FindFirstChild("Part") or Mob:FindFirstChild("Base") or Mob:FindFirstChild("hitbox") or Mob:FindFirstChild("Hitbox") or Mob:FindFirstChild("EasterGiantEgg") or Mob:FindFirstChild("Collider") or Mob:FindFirstChild("HumanoidRootPart")
                        if not BlockerHitbox then
                            if IsDebug then
                                warn("JDRS:", MobName, "(blocker has no target part)")
                            end
                            IsAliveMobs -= 1
                            return
                        end
                        BlockerHitbox.Name = "Collider"
                        ISV.MobTable[Mob] = {IsBlocker = true}
                        if IsDebug then
                            print("JDRS:", MobName, "(added, blocker)")
                        end
                        return
                    end
                    if Mob.Parent then
                        local MobData
                        local AllocatedLoadTime = time()+5
                        repeat
                            if time() > AllocatedLoadTime then
                                if ISV.Debug then
                                    warn("JDRS:", MobName, "(exceeded load time)")
                                end
                                break
                            end
                            MobData = rMob:GetMobData(Mob)
                            task.wait()
                        until MobData

                        if MobData and (MobData.IsHunterPet or MobData.CanAttackMobs or MobData.CanAttackEntities) then
                            if IsDebug then
                                warn("JDRS:", MobName, "(familiar or summon)")
                            end
                            IsAliveMobs -= 1
                            return
                        end

                        if SV.IsRanged then
                            if MobData then
                                MobData.Collider.Size = MobData.Collider.Size/2
                            else
                                local MobCollider = Mob:WaitForChild("Collider", 5)
                                if MobCollider then
                                    MobCollider.Size = MobCollider.Size/2
                                end
                            end
                        end

                        if DelayBosses[MobName] then
                            if IsDebug then
                                print("JDRS:", MobName, "(prevent stuck)")
                            end
                            task.wait(1)
                        end

                        if PriorityMobs[MobName] then
                            ISV.MobTable[Mob] = {Priority = true}
                            if IsDebug then
                                print("JDRS:", MobName, "(added, priority)")
                            end
                            return
                        end
                        if MobData then
                            if MobData.Invincible then
                                ISV.MobTable[Mob] = {Invincible = true}
                                if IsDebug then
                                    print("JDRS:", MobName, "(added, invincible)")
                                end
                            else
                                ISV.MobTable[Mob] = {}
                                if IsDebug then
                                    print("JDRS:", MobName, "(added)")
                                end
                            end
                        else
                            ISV.MobTable[Mob] = {NoData = true}
                            if IsDebug then
                                print("JDRS:", MobName, "(added, no mob data)")
                            end
                        end
                    else
                        if IsDebug then
                            warn("JDRS:", MobName, "(didn't add, no parent)")
                        end
                        IsAliveMobs -= 1
                        return
                    end
                end
                ConnectionTable["ConnectMobCreated"] = Remotes:WaitForChild("Health_InstanceAdded").OnClientEvent:Connect(function(Mob)
                    repeat task.wait() until Mob.Parent ~= ReplicatedStorage
                    ValidMob(Mob)
                end)
                ConnectionTable["ConnectMobDied"] = Remotes:WaitForChild("Mobs_MobDied", math.huge).OnClientEvent:Connect(function(Name, Mob)
                    local CheckTable = ISV.MobTable[Mob]
                    if CheckTable then
                        ISV.MobTable[Mob] = nil
                        IsAliveMobs -= 1
                        if ISV.Debug then
                            warn("JDRS:", Name, "(died)")
                        end
                    end
                end)
                for Index, Mob in Mobs:GetChildren() do
                    ValidMob(Mob)
                end
                while not KillSwitch do
                    if not CanTarget then
                        CurrentMob = nil
                        task.wait()
                        continue
                    end

                    local TableReference = ISV.MobTable
                    local ClosestMob = nil
                    local ClosestMobDistance = BigNumber
                    local ClosestAvoidMob = nil
                    local ClosestAvoidDistance = BigNumber
                    local ClosestNoData = nil
                    local MobPriority = nil
                    for Mob, AddedTable in TableReference do
                        if not Mob then
                            continue
                        end
                        if not Mob.Parent then
                            if ISV.Debug then
                                warn("JDRS:", Mob.Name, "(no parent)")
                            end
                            TableReference[Mob] = nil
                            IsAliveMobs -= 1
                            continue
                        end
                        local HealthProperties = Mob:FindFirstChild("HealthProperties")
                        local Health = HealthProperties and HealthProperties:FindFirstChild("Health")
                        if Health and Health.Value == 0 then
                            if ISV.Debug then
                                warn("JDRS:", Mob.Name, "(zero health)")
                            end
                            TableReference[Mob] = nil
                            IsAliveMobs -= 1
                            continue
                        end
                        if AddedTable.IsBlocker then
                            ClosestMob = Mob
                            break
                        end
                        local MobData = rMob:GetMobData(Mob)
                        if AddedTable.NoData then
                            if MobData then
                                AddedTable.NoData = nil
                            else
                                ClosestNoData = Mob
                            end
                        end
                        if AddedTable.Priority then
                            if MobData and not MobData.Invincible then
                                MobPriority = true
                                ClosestMob = Mob
                                continue
                            else
                                continue
                            end
                        end
                        if MobPriority then
                            continue
                        end
                        if not MobData then
                            local MobCollider = Mob:FindFirstChild("Collider")
                            if MobCollider then
                                MobData = {Collider = MobCollider}
                            else
                                continue
                            end
                        end
                        if not MobData.Invincible then
                            local MobDistance = (MobData.Collider.Position - PlayerRoot.Position).Magnitude
                            if not MobData.BossTag then
                                if MobDistance < ClosestMobDistance then
                                    ClosestMob = Mob
                                    ClosestMobDistance = MobDistance
                                end
                            else
                                if MobDistance < ClosestAvoidDistance then
                                    ClosestAvoidMob = Mob
                                    ClosestAvoidDistance = MobDistance
                                end
                            end
                        end
                    end
                    TeleportMob = ClosestMob or ClosestAvoidMob or ClosestNoData
                    if ClosestMob then
                        IsBoss = false
                        CurrentMob = ClosestMob
                    elseif ClosestAvoidMob then
                        IsBoss = true
                        CurrentMob = ClosestAvoidMob
                    elseif ClosestNoData then
                        CurrentMob = ClosestNoData
                    else
                        CurrentMob = nil
                    end
                    task.wait()
                end
            else
                PriorityMobs["BOSSSeraphiel"] = nil
                for _, CheckForRuins in SV.Parties:GetChildren() do
                    if CheckForRuins:WaitForChild("RaidID").Value == 30 then
                        FakeSpawnParts["Part"] = true
                    end
                end
                local function ValidMob(Mob, MobName)
                    local IsDebug = ISV.Debug
                    IsAliveMobs += 1
                    if Mob.Parent and Mob.Parent == Workspace.Characters then
                        if IsDebug then
                            warn("JDRS:", Mob, "(is a player)")
                        end
                        IsAliveMobs -= 1
                        return
                    end
                    if not MobName then
                        MobName = Mob.Name
                    end
                    if FakeMobs[MobName] then
                        if IsDebug then
                            warn("JDRS:", Mob, "(fake mob)")
                        end
                        IsAliveMobs -= 1
                        return
                    end
                    if Blockers[MobName] then
                        local BlockerHitbox = Mob:FindFirstChild("Part") or Mob:FindFirstChild("Base") or Mob:FindFirstChild("hitbox") or Mob:FindFirstChild("Hitbox") or Mob:FindFirstChild("EasterGiantEgg") or Mob:FindFirstChild("Collider")
                        if not BlockerHitbox then
                            return
                        end
                        BlockerHitbox.Name = "Collider"
                        ISV.MobTable[Mob] = {IsBlocker = true}
                        if IsDebug then
                            print("JDRS:", MobName, "(added, blocker)")
                        end
                        return
                    end
                    if Mob.Parent then
                        if Summons[MobName] then
                            if IsDebug then
                                warn("JDRS:", MobName, "(summon)")
                            end
                            IsAliveMobs -= 1
                            return
                        end
                        if DontAttackBosses[MobName] then
                            if IsDebug then
                                warn("JDRS:", MobName, "(bad boss)")
                            end
                            IsAliveMobs -= 1
                            return
                        end
                        local FromSpawnPart = Mob:WaitForChild("FromSpawnPart", 2)
                        if FromSpawnPart and FromSpawnPart.Value and FakeSpawnParts[tostring(FromSpawnPart.Value)] then
                            if IsDebug then
                                warn("JDRS:", MobName, "(fake mob)")
                            end
                            IsAliveMobs -= 1
                            return
                        end
                        local MobProperties = Mob:WaitForChild("MobProperties", 2)
                        local Owner = MobProperties and MobProperties:WaitForChild("Owner", 2)
                        if Owner and Owner.Value then
                            if IsDebug then
                                warn("JDRS:", MobName, "(familiar)")
                            end
                            IsAliveMobs -= 1
                            return
                        end
                        local ShrinkMob = ShrinkCollider[MobName]
                        if ShrinkMob then
                            local MobCollider = Mob:WaitForChild("Collider", 2)
                            if MobCollider then
                                MobCollider.Size = ShrinkMob
                            end
                        end
                        if DelayBosses[MobName] then
                            task.wait(1)
                        end
                        if PriorityMobs[MobName] then
                            ISV.MobTable[Mob] = {Priority = true}
                            if IsDebug then
                                print("JDRS:", MobName, "(priority)")
                            end
                            return
                        end
                        ISV.MobTable[Mob] = {}
                        if IsDebug then
                            print("JDRS:", MobName, "(added)")
                        end
                    end
                end
                ConnectionTable["ConnectMobCreated"] = Remotes:WaitForChild("Health_InstanceAdded").OnClientEvent:Connect(function(Mob)
                    repeat task.wait() until Mob.Parent ~= ReplicatedStorage
                    ValidMob(Mob)
                end)
                ConnectionTable["ConnectMobDied"] = Remotes:WaitForChild("Mobs_MobDied", math.huge).OnClientEvent:Connect(function(Name, Mob)
                    local CheckTable = ISV.MobTable[Mob]
                    if CheckTable then
                        ISV.MobTable[Mob] = nil
                        IsAliveMobs -= 1
                        if ISV.Debug then
                            warn("JDRS:", Name, "(died)")
                        end
                    end
                end)
                for Index, Mob in Mobs:GetChildren() do
                    task.spawn(function()
                        ValidMob(Mob)
                    end)
                end
                while not KillSwitch do
                    if not CanTarget then
                        CurrentMob = nil
                        task.wait()
                        continue
                    end
                    local TableReference = ISV.MobTable
                    local ClosestMob = nil
                    local ClosestMobDistance = math.huge
                    local ClosestAvoidMob = nil
                    local ClosestAvoidDistance = math.huge
                    local MobPriority = nil

                    for Mob, AddedTable in TableReference do
                        if not Mob.Parent then
                            TableReference[Mob] = nil
                            IsAliveMobs -= 1
                            if ISV.Debug then
                                warn("JDRS:", Mob.Name, "(no parent)")
                            end
                            continue
                        end
                        local MobHealthProperties = Mob:FindFirstChild("HealthProperties")
                        local MobHealth = MobHealthProperties and MobHealthProperties:FindFirstChild("Health")
                        if MobHealth and MobHealth.Value == 0 then
                            TableReference[Mob] = nil
                            IsAliveMobs -= 1
                            if ISV.Debug then
                                warn("JDRS:", Mob.Name, "(zero health)")
                            end
                            continue
                        end
                        if AddedTable.Invincible then
                            continue
                        end
                        local MobCollider = Mob:FindFirstChild("Collider")
                        if not MobCollider then
                            continue
                        end
                        if AddedTable.IsBlocker then
                            ClosestMob = Mob
                            break
                        end
                        if AddedTable.Priority then
                            MobPriority = true
                            ClosestMob = Mob
                            continue
                        end
                        if MobPriority then
                            continue
                        end
                        local MobDistance = (PlayerCollider.Position - MobCollider.Position).Magnitude
                        if AvoidMobs[Mob.Name] then
                            if MobDistance < ClosestAvoidDistance then
                                ClosestAvoidDistance = MobDistance
                                ClosestAvoidMob = Mob
                            end
                        else
                            if MobDistance < ClosestMobDistance then
                                ClosestMobDistance = MobDistance
                                ClosestMob = Mob
                            end
                        end
                    end
                    TeleportMob = ClosestMob or ClosestAvoidMob
                    if ClosestMob and ClosestMobDistance then
                        IsBoss = false
                        CurrentMob = ClosestMob
                    elseif not ClosestMob and ClosestAvoidMob and ClosestAvoidDistance then
                        IsBoss = true
                        CurrentMob = ClosestAvoidMob
                    else
                        CurrentMob = nil
                    end
                    task.wait()
                end
            end
        end)
        if not Success then
            SaveErrorToFile("MOB SCANNER", Result)
        end
    end
end

SetGlobal("ping once unlocked")
local function PingOnceUnlocked(UnlockedClass)
    local Success, Result = pcall(function()
        local MessageContent = {
            ["username"] = "Mastery tracker",
            ["content"] = string.format(
                "Unlocked class %s on %s\n-#%s",
                UnlockedClass, PlayerName, DiscordPingType
            )
        }
        RequestMessage(SV.DiscordWebhookLink, MessageContent, false)
    end)
end

SetGlobal("ping for cap")
local function PingForCap(PingThing)
    local Success, Result = pcall(function()
        local MessageContent = {
            ["username"] = "Limit tracker",
            ["content"] = string.format(
                "%s clear limit reached on %s\n-#%s",
                PingThing, PlayerName, DiscordPingType
            )
        }
        RequestMessage(SV.DiscordWebhookLink, MessageContent, false)
    end)
end

SetGlobal("get difficulty")
local function GetDifficulty()
    return Remotes:WaitForChild("Missions_GetDifficulty", math.huge):InvokeServer()
end

SetGlobal("get lives")
local function GetLives()
    return Remotes:WaitForChild("Missions_GetCurrentLives", math.huge):InvokeServer()
end

SetGlobal("party leader check")
local function PartyLeaderCheck()
    if SV.Parties then
        local PartyLeader = Remotes:WaitForChild("Party_GetPartyData", math.huge):InvokeServer().Leader.Value
        if PlayerName == PartyLeader then
            return true
        else
            return
        end
    end
end

SetGlobal("replay dungeon loop")
local function ReplayDungeonLoop(Mission, Difficulty)
    local Success, Result = pcall(function()
        if Mission == 49 then
            Mission = 1
        end
        CleanUpScript()
        while not ScriptUnloaded do
            if ISV.Debug then
                print(string.format(
                    "Attempting to replay %* on difficulty %*",
                    Mission, Difficulty
                ))
            end
            Remotes:WaitForChild("Teleport_StartRaid", math.huge):FireServer(Mission, Difficulty)
            task.wait(10)
        end
    end)
    if not Success then
        SaveErrorToFile("REPLAY DUNGEON", Result)
    end
end

SetGlobal("rejoin last dungeon")
local function RejoinLastDungeon(DoRejoin)
    if SV.CreatingRejoinFile then
        return
    end
    local Success, Result = pcall(function()
        local RejoinFileName = "JDRS/" ..PlayerName.. "_Rejoin"
        if isfile(RejoinFileName) then
            SV.CreatingRejoinFile = true
            local RejoinData = nil
            pcall(function()
                RejoinData = HttpService:JSONDecode(readfile(RejoinFileName))
            end)
            if RejoinData and RejoinData ~= "" then
                local RejoinDungeon = RejoinData.Dungeon
                local RejoinDifficulty = RejoinData.RejoinDifficulty
                local RejoinTime = RejoinData.DisconnectedTime
                delfile(RejoinFileName)
                if RejoinTime + 300 > os.time() then
                    KillSwitch = true
                    ReplayDungeonLoop(RejoinDungeon, RejoinDifficulty)
                end
            else
                delfile(RejoinFileName)
                if IsEventDungeon then
                    ReplayDungeonLoop(ISV.CurrentDungeonID, 1)
                elseif IsDungeon then
                    ReplayDungeonLoop(ISV.CurrentDungeonID, 6)
                elseif IsTower then
                    ReplayDungeonLoop(ISV.CurrentDungeonID, false)
                end
            end
        end
        if DoRejoin then
            SV.CreatingRejoinFile = true
            local Difficulty = ISV.LoggedDifficulty
            if IsTower then
                Difficulty = nil
            end
            DungeonData = {
                Dungeon = ISV.MissionId,
                RejoinDifficulty = Difficulty,
                DisconnectedTime = os.time()
            }
            writefile(RejoinFileName, HttpService:JSONEncode(DungeonData))
            TeleportService:Teleport(tonumber("4310463616"), LocalPlayer)
            task.wait(5)
            TeleportService:Teleport(tonumber(StringPlaceID), LocalPlayer)
        end
    end)
    if not Success then
        SaveErrorToFile("REJOIN LAST DUNGEON", Result)
    end
end

SetGlobal("wait for game crash")
do
    CoreGui:WaitForChild("RobloxPromptGui", math.huge):WaitForChild("promptOverlay", math.huge).ChildAdded:Once(function()
        RejoinLastDungeon(true)
    end)
end

SetGlobal("restart dungeon")
local function RestartDungeon(RestartBypass)
    if not (SV.ReplayMission or SV.DoingGuildDungeon or RestartBypass) then 
        return
    end
    if SV.TowerChestDelay then
        task.wait(6)
    end
    local Difficulty = GetDifficulty()
    if not PartyLeaderCheck() then
        Remotes:WaitForChild("Missions_LeaveChoice", math.huge):FireServer(true)
        Remotes:WaitForChild("Missions_NotifyReadyToLeave", math.huge):FireServer()
        return
    end
    Library:Notify("Teleporting...", SV.RestartDungeonDelay)
    KillSwitch = true
    task.wait(SV.RestartDungeonDelay)
    if IsTower then
        Difficulty = nil
    end
    if GetLives() == 0 then
        ReplayDungeonLoop(ISV.MissionId, Difficulty)
    end
    if SV.DoingGuildDungeon and not SV.IsNightmareDungeon then
        if not (ISV.MissionId == 42 and Difficulty == 5) then
            if Difficulty == 1 and not IsTower then
                Library:Notify("Moving to challenge mode", 1)
                ReplayDungeonLoop(ISV.MissionId, 5)
            else
                local NextDungeon
                for DungeonIndex, Dungeon in SV.DungeonListTable do
                    if Dungeon.DungeonID == ISV.MissionId then
                        NextDungeon = DungeonIndex - 1
                        break
                    end
                end
                local NextDungeonReference = SV.DungeonListTable[NextDungeon]
                Library:Notify("Moving to " ..NextDungeonReference.DungeonName, 1)
                if NextDungeonReference.Level > 0 then
                    ReplayDungeonLoop(NextDungeonReference.DungeonID, 1)
                else
                    ReplayDungeonLoop(NextDungeonReference.DungeonID, nil)
                end
            end
        else
            local RestartChoice = Options.DoAllDropdown.Value
            if RestartChoice == "Stop" then
                Library:Notify("Finished doing all dungeons", 9999999999999999)
                return
            elseif RestartChoice == "Loop" then
                ReplayDungeonLoop(38, nil)
            elseif RestartChoice == "Loop w/o inf" then
                ReplayDungeonLoop(21, nil)
            elseif RestartChoice == "Loop w/o towers" then
                ReplayDungeonLoop(1, 1)
            elseif RestartChoice == "Play nightmare dungeons" then
                ReplayDungeonLoop(1005, 6)
            end
        end
    end
    if SV.IsNightmareDungeon and SV.PrioNmDCount and ISV.PlayerLevel == 175 then
        local GetCurrentDailyDungeon = Remotes:WaitForChild("Missions_GetCurrentDailyDungeon", math.huge):InvokeServer()
        local SelectedDungeon = ISV.MissionId
        local SelectedDungeonSpecialPerk
        local SelectedDungeonLength = 9999
        for Index, Data in GetCurrentDailyDungeon do
            local InternalID = Data.InternalID
            for DungeonIndex in Options.PrioNmDropdown.Value do
                local DungeonData = SV.PrioritizedNightmareDungeons[DungeonIndex]
                if InternalID == DungeonData.ID then
                    if DungeonData.SpecialPerk then
                        if not SelectedDungeonSpecialPerk then
                            SelectedDungeonSpecialPerk = true
                            SelectedDungeon = Data.ID
                            SelectedDungeonLength = DungeonData.Length
                        elseif DungeonData.Length < SelectedDungeonLength then
                            SelectedDungeon = Data.ID
                            SelectedDungeonLength = DungeonData.Length
                        end
                    elseif not SelectedDungeonSpecialPerk and DungeonData.Length < SelectedDungeonLength then
                        SelectedDungeon = Data.ID
                        SelectedDungeonLength = DungeonData.Length
                    end
                end
            end
        end
        ReplayDungeonLoop(SelectedDungeon, Difficulty)
    end
    if SV.AutoLeveling and not IsEventDungeon then
        local CheckPartySize = Players:GetChildren()
        local LowestLevel = math.huge
        if #CheckPartySize > 1 then
            for Index, Player in CheckPartySize do
                local MemberLevel = Player:GetAttribute("Level")
                if MemberLevel and MemberLevel < LowestLevel then
                    LowestLevel = MemberLevel
                end
            end
        else
            LowestLevel = LocalPlayer:GetAttribute("Level")
        end
        for Index, AutoLevelingDungeon in SV.DungeonListTable do
            if LowestLevel >= AutoLevelingDungeon.Level then
                if AutoLevelingDungeon.DungeonID == ISV.MissionId then
                    Library:Notify("Replaying: " ..AutoLevelingDungeon.DungeonName, 2)
                else
                    Library:Notify("Moving to: " ..AutoLevelingDungeon.DungeonName, 2)
                end
                ReplayDungeonLoop(AutoLevelingDungeon.DungeonID, 5)
            end
        end
    end
    if SV.RandomNightmareDungeon and SV.IsNightmareDungeon then
        ISV.MissionId = SV.RandomNightmareDungeon
    end
    ReplayDungeonLoop(ISV.MissionId, Difficulty)
end

SetGlobal("collect chests")
local function CollectChests()
    local ExtraChestCheck = true
    local ChestDrops = {}
    local rItems = false
    local Success, Result = pcall(function()
        if SV.CanRequire then
            rItems = require(Items)
        end
        local Success1, Result1 = pcall(function()
            ExtraChestCheck = MarketplaceService:UserOwnsGamePassAsync(PlayerID, 8136250)
        end)
        if not Success1 then
            warn("unable to check if user owns extra chest gamepass")
        end
        local MissionPrize = Remotes:WaitForChild("Missions_GetMissionPrize", math.huge)
        for ChestIndex = 1, 4 do
            if ChestIndex == 4 and not ExtraChestCheck then
                break
            end

            local ChestPrize
            if ChestIndex == 1 then
                ChestPrize = MissionPrize:InvokeServer(true)
            else
                ChestPrize = MissionPrize:InvokeServer()
            end

            if ChestPrize then
                if rItems then
                    ChestPrize = rItems[tostring(ChestPrize)].DisplayKey
                end
                if Library then
                    Library:Notify("Chest reward: " ..tostring(ChestPrize), 1)
                end
                table.insert(ChestDrops, ChestPrize)
            end
        end
        task.wait(.5)
    end)
    if not Success then
        SaveErrorToFile("COLLECT DUNGEON CHESTS", Result)
    end
    return ChestDrops
end

SetGlobal("collect tower chests")
local function CollectTowerChests()
    CheckForCharacter()
    if IsTower then
        local Success, Result = pcall(function()
            local OpenChest = Remotes:WaitForChild("Chests_OpenChest", math.huge)
            if SV.CanRequire and debug and getupvalue then
                local ChestScript = debug.getupvalue(require(Chests).Start, 12)
                for ChestKey, ChestPath in ChestScript do
                    OpenChest:FireServer(ChestKey)
                end
            else
                local ChestNames = {
                    "RaidChestBlue", "RaidChestGold", "RaidChestSilver", "HeavenlyRaidChest"
                }
                for Index, ChestName in ChestNames do
                    local Chest = Workspace:FindFirstChild(ChestName)
                    if Chest and Chest.Parent then
                        task.spawn(function()
                            while Chest.Parent do
                                Chest:PivotTo(CFrame.new(PlayerRoot.Position))
                                task.wait()
                            end
                        end)
                    end
                end
            end
        end)
        if not Success then
            SaveErrorToFile("COLLECT TOWER CHEST", Result)
        end
    end
end

SetGlobal("claim all quests")
local function ClaimAllQuests()
    local Success, Result = pcall(function()
        local ProfileQuests = PlayerProfile:WaitForChild("Quests", math.huge)
        local Active = ProfileQuests:WaitForChild("Active", math.huge)
        if SV.ClaimGuildQuests then
            local GetDailyGuildQuests = require(Quests):GetDailyGuildQuests()
            for Difficulty, Data in GetDailyGuildQuests do
                local QuestID = Data.ID
                if not Remotes:WaitForChild("Quests_GuildDailyIsClaimed", math.huge):InvokeServer(QuestID) then
                    if Active:FindFirstChild(QuestID) then
                        for i = 1, 2 do
                            Remotes:WaitForChild("Quests_ClaimDailyGuildQuest", math.huge):FireServer(QuestID)
                        end
                        task.wait(1.5)
                    end
                end
            end
        end
        local ClaimQuest = Remotes:WaitForChild("Quests_ClaimQuest", math.huge)
        if ClaimQuest then
            for _, ActiveQuest in Active:GetChildren() do
                ClaimQuest:FireServer(tonumber(ActiveQuest.Name))
            end
        end
    end)
    if not Success then
        local ExtraMessage
        if Result:find("IsSeasonActive") then
            ExtraMessage = "\"IsSeasonActive\" is a in-game error not caused by the script"
        end
        SaveErrorToFile("CLAIM QUESTS", Result, ExtraMessage)
    end
end

SetGlobal("getting current dungeon")
local function GetDungeonImage()
    local Success, Result = pcall(function()
        if not SV.CanRequire then
            ISV.DungeonImage = ""
            return
        end
        local ImageURL = ""
        local GetCurrentMissionData = require(Missions):GetCurrentMissionData() 
        local ImageID = GetCurrentMissionData.DungeonID or GetCurrentMissionData.ImageID or "3815150377"
        ImageID = tostring(ImageID):match("%d+")
        if ISV.MissionId == 43 then
            ImageID = tonumber("15046578670")
        end
        local ImageFile = "JDRS/DungeonImages"
        if not isfile(ImageFile) then
            local ReturnedImage = game:HttpGet(("https://thumbnails.roblox.com/v1/assets?assetIds="..ImageID.."&size=420x420&format=Png"))
            ReturnedImage = HttpService:JSONDecode(ReturnedImage).data[1]
            writefile(ImageFile, HttpService:JSONEncode({Images = { [tostring(ImageID)] = {ReturnedImage.imageUrl, os.time()+604800}}}))
            ImageURL= ReturnedImage.imageUrl
        else
            local ReadImageFile = HttpService:JSONDecode(readfile(ImageFile)).Images
            local ImageCached = ReadImageFile[ImageID]
            if not ImageCached or ImageCached[2] <= os.time() or string.find(tostring(ImageCached[1]), "token") then
                local RemakeTable = {}
                for i, o in ReadImageFile do
                    RemakeTable[i] = {table.unpack(o)}
                end
                local ReturnedImage = game:HttpGet(("https://thumbnails.roblox.com/v1/assets?assetIds="..ImageID.."&size=420x420&format=Png"))
                ReturnedImage = HttpService:JSONDecode(ReturnedImage).data[1]
                RemakeTable[tostring(ImageID)] = { ReturnedImage.imageUrl, os.time()+604800}
                writefile(ImageFile, HttpService:JSONEncode({Images = RemakeTable}))
                ImageURL= ReturnedImage.imageUrl
            else
                ImageURL = ImageCached[1]
            end
        end
        if string.find(tostring(ImageURL), "token") then
            ImageURL = ""
        end
        ISV.DungeonImage = ImageURL
    end)
    if not Success then
         ISV.DungeonImage = ""
    end
end

SetGlobal("connect mission finished")
local function ConnectMissionFinished()
    if IsDungeon then
        local MissionFinished = Remotes:WaitForChild("Missions_MissionFinished", math.huge)
        ConnectionTable["MissionFinished"] = MissionFinished.OnClientEvent:Once(function(EndTime, PlayersInDungeon, Lost)
            SV.DungeonCompletionTime = SecondsToString(EndTime)
            if SV.ShowTime then
                Library:Notify("Completed in " ..SV.DungeonCompletionTime)
            end
            if ISV.Debug then
                print("AutoLeveling check")
            end
            if SV.AutoLeveling then
                ClaimAllQuests()
            end
            if ISV.Debug then
                print("Collect chest check")
            end
            local ChestDrops = {"none"}
            if SV.CollectDungeonChest then
                ChestDrops = CollectChests()
            end
            if SV.DungeonPing then
                local EmbedColor = 65280
                local CompletionStatus = "completed"
                local DungeonName = "unknown"
                local PlayersInDungeon = Players:GetChildren()
                if Lost then
                    EmbedColor = 16711680
                    CompletionStatus = "failed"
                end
                if SV.CanRequire then
                    DungeonName = require(Missions):GetCurrentMissionData().NameTag
                else
                    DungeoName = DungeonName.. "(missing require())"
                end
                if Toggles.ShowPlayersToggle.Value then
                    local PlayerTable = {}
                    for Index, Player in PlayersInDungeon do
                        table.insert(PlayerTable, Player.Name)
                    end
                    PlayersInDungeon = table.concat(PlayerTable, "`, `")
                else
                    PlayersInDungeon = #PlayersInDungeon
                end
                if not ISV.DungeonImage then
                    GetDungeonImage()
                end
                local MessageContent = {
                    ["username"] = "Dungeon logger",
                    ["embeds"] = {
                        {
                            ["description"] = string.format(
                                "**Dungeon** `%s`\n**Time:** `%s`\n**Party size:** `%*`\n**Chest drops:** `%*`",
                                DungeonName, SV.DungeonCompletionTime, PlayersInDungeon, table.concat(ChestDrops, "`, `")
                            ),
                            ["type"] = "rich",
                            ["color"] = EmbedColor,
                            ["thumbnail"] = { url = ISV.DungeonImage },
                        }
                    }
                }
                RequestMessage(SV.DiscordWebhookLink, MessageContent, false)
            end
            repeat
                task.wait(1)
                if ISV.Debug then
                    print(string.format(
                        "Sell check: %d, Equip check: %d",
                        SellItemCheck, EquipInProgress
                    ))
                end
            until SellItemCheck == 0 and EquipInProgress == 0
            RestartDungeon()
        end)
    end
end

SetGlobal("connect tower finished")
local function ConnectTowerFinished()
    local TowerFinished 
    if ISV.MissionId == 39 then
        TowerFinished = ReplicatedStorage:WaitForChild("MissionScripts", math.huge):WaitForChild("39", math.huge):WaitForChild("TowerFinished", math.huge)
    elseif ISV.MissionId == 56 then
        TowerFinished = ReplicatedStorage:WaitForChild("MissionScripts", math.huge):WaitForChild("56", math.huge):WaitForChild("TowerFinished", math.huge)
    else
        TowerFinished = Remotes:WaitForChild("Towers_TowerFinished", math.huge)
    end
    ConnectionTable["TowerFinished"] = TowerFinished.OnClientEvent:Once(function(Countdown, EndTime)
        SV.DungeonCompletionTime = SecondsToString(EndTime)
        if SV.ShowTime then
            Library:Notify("Completed in " ..SV.DungeonCompletionTime)
        end
        if SV.DungeonPing then
            local EmbedColor = 65280
            local CompletionStatus = "completed"
            local DungeonName = "unknown"
            local PlayersInDungeon = Players:GetChildren()
            if Lost then
                EmbedColor = 16711680
                CompletionStatus = "failed"
            end
            if SV.CanRequire then
                DungeonName = require(Missions):GetCurrentMissionData().NameTag
            else
                DungeoName = DungeonName.. "(missing require())"
            end
            if Toggles.ShowPlayersToggle.Value then
                local PlayerTable = {}
                for Index, Player in PlayersInDungeon do
                    table.insert(PlayerTable, Player.Name)
                end
                PlayersInDungeon = table.concat(PlayerTable, "`, `")
            else
                PlayersInDungeon = #PlayersInDungeon
            end
            if not ISV.DungeonImage then
                GetDungeonImage()
            end
            local MessageContent = {
                ["username"] = "Dungeon logger",
                ["embeds"] = {
                    {
                        ["description"] = string.format(
                            "**Dungeon** `%s`\n**Time:** `%s`\n**Party size:** `%*`",
                            DungeonName, SV.DungeonCompletionTime, PlayersInDungeon
                        ),
                        ["type"] = "rich",
                        ["color"] = EmbedColor,
                        ["thumbnail"] = { url = ISV.DungeonImage },
                    }
                }
            }
            RequestMessage(SV.DiscordWebhookLink, MessageContent, false)
        end
        RestartDungeon()
    end)
end

SetGlobal("get rarity")
local function GetRarity(Item)
    if SV.Items then
        local ItemRef = SV.Items[Item.Name]
        if ItemRef.Type and (ItemRef.Type == "Pet" or ItemRef.Type == "Weapon" or ItemRef.Type == "Armor" or ItemRef.Type == "Charm") then
            local ItemRarity
            if ItemRef.Type == "Pet" then
                ItemRarity = ItemRef.Variants[Item:WaitForChild("Variant", 10).Value][4]
            else
                ItemRarity = ItemRef.Rarity
            end
            if ItemRef.Type == "Charm" then
                if ItemRarity == 5 then
                    return 5, 1
                else
                    return 4
                end
            end
            if ItemRarity == 7 then
                return 7
            elseif ItemRarity == 5 then
                return 5, 3
            elseif ItemRarity == 4 then 
                return 4, 2
            elseif ItemRarity == 3 then
                return 3, 1
            else
                return 2
            end
        else
            return "NotEquipment"
        end
    else
        task.wait(1.5)
        local Upgrade = Item:FindFirstChild("UpgradeLimit")
        if (Upgrade and Upgrade.Value == 20) then
            return 7
        elseif Item:FindFirstChild("Perk3") then
            return 5, 3
        elseif Item:FindFirstChild("Perk2") then
            return 4, 2
        elseif Item:FindFirstChild("Perk1") then
            return 3, 1
        elseif Uograde then
            return 2
        else
            return "NotEquipment"
        end
    end
end

SetGlobal("equip new item added")
local function EquipNewItemAdded()
    local Success, Result = pcall(function()
        local ScanInventory = ProfileInventory:WaitForChild("Items")
        local EquipSlots = {
            "Armor", "Primary", "Offhand"
        }
        local PlayerEquips = ReplicatedStorage.PlayerEquips[LocalPlayer.Name]
        local EquipItem = Remotes:WaitForChild("Inventory_EquipItem", math.huge)
        ConnectionTable["ConnectEquipNewItems"] = ScanInventory.ChildAdded:Connect(function(NewItem)
            local Success1, Result1 = pcall(function()
                EquipInProgress = EquipInProgress + 1
                task.wait(1)
                if ISV.Debug then
                    print("Checking equip: ", NewItem)
                end
                if not NewItem:FindFirstChild("Level") then
                    EquipInProgress = EquipInProgress - 1
                    return
                end
                for Index, Slot in EquipSlots do
                    if NewItem and NewItem.Parent and NewItem.Parent.Name ~= "Items" then
                        return  
                    end
                    local CheckSlot = PlayerEquips[Slot]
                    local NewItemLevel = NewItem:FindFirstChild("Level")
                    local OldItem = CheckSlot:FindFirstChildWhichIsA("Folder")
                    if NewItemLevel and OldItem then
                        OldItemLevel = OldItem:FindFirstChild("Level")
                        if OldItemLevel and (NewItemLevel.Value >= OldItemLevel.Value) then
                            if NewItemLevel.Value == OldItemLevel.Value then
                                local NewItemRarity = GetRarity(NewItem)
                                local OldItemRarity = GetRarity(OldItem)
                                if typeof(NewItemRarity) == "number" and typeof(OldItemRarity) == "number" and NewItemRarity > OldItemRarity then
                                    EquipItem:FireServer(NewItem, CheckSlot)
                                    continue
                                else
                                    continue
                                end
                            end
                            EquipItem:FireServer(NewItem, CheckSlot)
                        end
                    end
                end
                task.wait(1)
                EquipInProgress = EquipInProgress - 1
            end)
            if not Success1 then
                SaveErrorToFile("SCAN ITEM TO EQUIP", tostring(Result1), NewItem)
            end
        end)
    end)
    if not Success then
        SaveErrorToFile("EQUIP NEW ITEM", Result)
    end
end

SetGlobal("get player size")
local function GetPlayerSize()
    return PlayerCollider.Size.Y / 2 or 0
end

SetGlobal("collect coins")
local function CollectCoins()
    CheckForCharacter()
    if SV.CanRequire and debug and getupvalue then
        local Success, Result = pcall(function()
            local rDrops = debug.getupvalue(require(Drops).Start, 6)
            local CoinEvent = Remotes:WaitForChild("Drops_CoinEvent", math.huge)
            for DropIndex, CoinDrop in rDrops do
                CoinDrop.model:Destroy()
                CoinDrop.followPart:Destroy()
                CoinEvent:FireServer(CoinDrop.id)
            end
        end)
        if not Success then
            SaveErrorToFile("COLLECT DROP", Result)
        end
    else
        local Success, Result = pcall(function()
            local CoinFolder = Workspace:WaitForChild("Coins", math.huge)
            local PlayerSize = GetPlayerSize()
            for _, CoinChild in CoinFolder:GetChildren() do
                if CoinChild:IsA("Part") then
                    while CoinChild.Parent do
                        CoinChild.CanCollide = false
                        CoinChild.Anchored = true
                        CoinChild.CFrame = CFrame.new(PlayerRoot.Position.X, PlayerRoot.Position.Y-GetPlayerSize(), PlayerRoot.Position.Z)
                        task.wait(0.1)
                    end
                end
            end
        end)
        if not Success then
            SaveErrorToFile("COLLECT DROP FALLBACK", Result)
        end
    end
end

SetGlobal("get guild")
local function GetGuild(Player)
    return Player:GetAttribute("GuildTag") or "❌"
end

local function IsTowerEgg(Item)
    if Item and Item.Name and SV.TowerEggList and SV.TowerEggList[Item.Name] then
        return true
    end
end

SetGlobal("sell item")
local function SellItem(Item, SellContext)
    if ISV.Debug then
        if SellContext then
            warn(SellContext)
        else
            warn("Selling item: ", Item.Name)
        end
    end
    local Success, Result = pcall(function()
        Remotes:WaitForChild("Drops_SellItems", math.huge):InvokeServer({Item})
        if Library then
            Library:Notify("<font color='#FCCE7E'>Sold item:</font> " ..tostring(Item), 1)
        end
        SellItemCheck = SellItemCheck - 1
    end)
    if not Success then
        SaveErrorToFile("SELL", Result)
    end
end

SetGlobal("buy from local shop")
local function BuyFromLocalShop(ShopData, PurchaseData)
    local IsDebug = ISV.Debug
    if not PurchaseData then
        Library:Notify("No item selected")
        return
    end
    local Currency = ShopData.ShopInfo.Currency
    local ShopName = ShopData.ShopInfo.ShopName
    local Item = PurchaseData.InternalName
    local ItemName = PurchaseData.VisualName
    local ItemPrice = PurchaseData.CoinPrice
    if IsDebug then
        print(string.format(
            "JDRS: attempting to buy %* (%*) for %*",
            ItemName, Item, ItemPrice
        ))
    end
    if not (Item and ItemPrice and ItemName) then
        if IsDebug then
            warn(string.format(
                "JDRS: purchase failed, do these variables exist?\nItem name: %*\nInternal name: %*\nItem price: %*",
                    ItemName, Item, ItemPrice
            ))
        end
        return
    end
    local BuyLocal = Remotes:FindFirstChild("CoinShop_Buy")
    local Coins = ProfileInventory:WaitForChild("Items", math.huge):FindFirstChild(Currency)
    if not (Coins and BuyLocal) then
        if IsDebug then
            warn(string.format(
                "JDRS: purchase failed, do these variables exist?\nRemote path: %*\nCurrency path: %*",
                    BuyLocal and BuyLocal:GetFullName() or nil,
                    Coins and string.gsub(Coins:GetFullName(), PlayerName, "LocalPlayer") or "does player have currency "..tostring(Currency).."?"
            ))
        end
        return
    end
    local CoinCount = Coins and Coins:FindFirstChild("Count")
    if not (CoinCount and tonumber(CoinCount.Value) >= ItemPrice) then
        if IsDebug then
            warn(string.format(
                "JDRS: player doesn't have enough for %* (%*).\nItem costs %*, but player has %*",
                ItemName, Item, ItemPrice, CoinCount and CoinCount.Value or nil
            ))
        end
        return
    end
    local Success, Result = pcall(function()
        BuyLocal:InvokeServer(ShopName, Shop.LocalShops[ShopName].Items[Item])
    end)
    if not Success then
        SaveErrorToFile("BUY FROM LOCAL SHOP", Result)
        return
    end
    Library:Notify("Purchased " ..ItemName.. "!", 1)
    task.wait(0.6)
    return true
end

SetGlobal("buy from egg shop")
local function BuyFromEggShop(Currency, Egg, EggPrice, EggName)
    if ISV.Debug then
        print("Buy egg with data: ", Currency, Egg, EggPrice, EggName)
    end
    local BuyEgg = Remotes:FindFirstChild("Pets_BuyEgg")
    if Currency == "Gold" then
        local ProfileCurrency = PlayerProfile:FindFirstChild("Currency")
        if not (BuyEgg and ProfileCurrency) then
            return
        end
        local Gold = ProfileCurrency and ProfileCurrency:FindFirstChild("Gold")
        if not (Gold and tonumber(Gold.Value) >= EggPrice) then
            return
        end
    elseif Currency == "Crystal" then
        local GetCrystals = Remotes:WaitForChild("Crystals_GetCrystals", math.huge):InvokeServer()
        if not (GetCrystals and GetCrystals >= EggPrice) then
            return
        end
    end
    BuyEgg:FireServer(Egg, Currency)
    Library:Notify("Purchased " ..EggName.. "!", 1)
    return true
end

SetGlobal("open menu")
local function OpenMenu(Menu)
    local Success, Result = pcall(function()
        require(Client.Gui):Get(Menu):Open(true)
    end)
    if not Success then
        Library:Notify("Function is unsupported by your executor", 5)
    end
end

SetGlobal("upgrade to max")
local function UpgradeToMax(Slot)
    if IsDungeon or IsWorld then
        local pUpgrade, pUpgradeFail = pcall(function()
            local EquipmentPiece = ReplicatedStorage.PlayerEquips[PlayerName][Slot]:FindFirstChildWhichIsA("Folder")
            local ItemUpgradePath = Remotes:FindFirstChild("ItemUpgrade_Upgrade")
            if not (EquipmentPiece and ItemUpgradePath) then
                return
            end
            if ISV.Debug then
                print("upgrading: ", EquipmentPiece)
            end
            for i = 1, 150 do
                ItemUpgradePath:FireServer(EquipmentPiece, false)
            end
            Library:Notify(Slot.. " has been upgraded", 1)
        end)
        if not pUpgrade then
            SaveErrorToFile("UPGRADE", tostring(pUpgradeFail))
        end
    end
end

SetGlobal("expand part size")
local function ExpandPartSize(Part)
    if ISV.Debug then
        print("Expanding part: ", Part.Name)
    end
    local PreviousTriggerSize = Part.Size
    Part.Size = Vector3.new(2048, 2048, 2048)
    task.wait(1)
    Part.Size = PreviousTriggerSize
end

SetGlobal("find part")
local function FindPart(Location, PartData)
    local MainParent
    local DeleteOnceFound
    if not Location then
        MainParent = MissionObjects
    elseif Location == "CheckpointGates" then
        MainParent = MissionObjects:WaitForChild("CheckpointGates", math.huge)
    elseif Location == "NoParent" then
        MainParent = Workspace
    elseif Location == "BossRoom" then
        MainParent = MissionObjects:WaitForChild("BossRoom", math.huge)
    elseif Location == "DeleteParts" then
        MainParent = Workspace
        DeleteOnceFound = true
    end


    for _, PartName in PartData do
        if type(PartName) == "string" then
            MainParent = MainParent:WaitForChild(PartName, math.huge)
        end
    end

    if DeleteOnceFound then
        MainParent:Destroy()
        MainParent = nil
        if PartData.MultipleExists then
            FindPart(Location, PartData)
        end
        return
    end

    local TouchInterest
    if PartData.DescendantCheck then
        for Index, Part in MainParent:GetDescendants() do
            if Part.ClassName == "TouchTransmitter" then
                MainParent = Part.Parent
                TouchInterest = Part
                break
            end
        end
    else 
        TouchInterest = MainParent:WaitForChild("TouchInterest", math.huge)
    end

    local StartingPartSize = MainParent.Size
    local StartingPartCollision = MainParent.CanCollide
    local StartingPosition = MainParent.Position
    if SV and SV.Autofarm then
        MainParent.Size = Vector3.new(1, 1, 1)
        MainParent.CanCollide = false
    end
    if SV then
        TeleportParts[MainParent] = {
            TouchPart = TouchInterest,
            OriginalLocation = StartingPosition,
            OriginalSize = StartingPartSize,
            OriginalCollision = StartingPartCollision,
            Regenerates = PartData.Regenerates or nil,
            AutoTouchTimer = PartData.AutoTouch and time()+1.5 or nil,
            DontTeleport = PartData.DontTeleport or nil
        }
        if PartData.Regenerates then
            while not KillSwitch do
                repeat
                    task.wait(0.5)
                until not TouchInterest.Parent or not TouchInterest.Parent and TouchInterest.Parent
                TouchInterest = MainParent:WaitForChild("TouchInterest", math.huge)
                if SV and SV.Autofarm then
                    MainParent.Size = Vector3.new(1, 1, 1)
                end
                MainParent.CanCollide = false
                TeleportParts[MainParent] = {
                    TouchPart = TouchInterest,
                    OriginalLocation = StartingPosition,
                    OriginalSize = StartingPartSize,
                    OriginalCollision = StartingPartCollision,
                    Regenerates = PartData.Regenerates or nil,
                    AutoTouchTimer = PartData.AutoTouch and time()+1.5 or nil,
                    DontTeleport = PartData.DontTeleport or nil
                }
                task.wait()
            end
        end
    end
end

SetGlobal("disconnect variables")
local function DisconnectVariable(Connection)
    if ConnectionTable[Connection] then
        ConnectionTable[Connection]:Disconnect()
        ConnectionTable[Connection] = nil
    end
end

SetGlobal("teleport stand part")
local function TeleportStandPart()
    if PlayerStandPart then
        PlayerStandPart.CFrame = CFrame.new(PlayerCollider.Position.X, (PlayerCollider.Position.Y-StandPartHeight), PlayerCollider.Position.Z)
    end
end

SetGlobal("dodge current attack")
local function DodgeCurrentAttack(DelayBeforeDodge, DodgeLength, AttackName, AdjustZ)
    local Success, Result = pcall(function()
        if EventOverride then
            return
        end
        local ZOffset = AdjustZ or 0
        local AttackName = AttackName or "[no name for attack given]"
        SV.DodgingAttack = true
        task.wait(DelayBeforeDodge)

        if SV.SafeKillaura then
            CanTarget = false
        end

        local DodgeStart = time() + DodgeLength
        local DodgePosition = Vector3.new(PlayerRoot.Position.X, PlayerRoot.Position.Y+200, PlayerRoot.Position.Z+ZOffset)
        Library:Notify("Dodging attack: "..AttackName, DodgeLength)
        while time() < DodgeStart and not EventOverride do
            TempStop = true
            PlayerRoot.CFrame = CFrame.new(DodgePosition)
            TeleportStandPart()
            task.wait()
        end
        TempStop = false
        CanTarget = true
        SV.DodgingAttack = nil
    end)
    if not Success then
        SaveErrorToFile("DODGING ATTACK", Result)
    end
end

SetGlobal("teleport to orb")
local function TeleportToOrb(Orb)
    CheckForCharacter()
    local Success, Result = pcall(function()
        while SV.DodgingAttack do
            task.wait()
        end

        local OrbPart = Orb:WaitForChild("Particles", 5) or false
        if not OrbPart then
            print("Unable to locate orb part")
            return
        end

        if SV.SafeKillaura then
            CanTarget = false
        end

        local TeleportStart = time() + 0.5
        while time() < TeleportStart do
            TempStop = true
            PlayerRoot.CFrame = CFrame.new(OrbPart.Position)
            TeleportStandPart()
            task.wait()
        end
        CanTarget = true
        TempStop = false
    end)
    if not Success then
        SaveErrorToFile("TELEPORT TO ORB", Result)
    end
end

SetGlobal("build attacks")
local function BuildAttackData(TargetTable, TargetIndex)
    TargetIndex = tostring(TargetIndex)
    local AttackSkills = TargetTable[TargetIndex].Skills
    if not AttackSkills then
        TargetTable[TargetIndex].Skills = {}
        for SkillIndex, SkillInfo in TargetTable[TargetIndex].SkillInfo do
            local NumberOfAttacks = SkillInfo[1]
            local AttackName = SkillInfo[2]
            local AttackCooldown = SkillInfo[3]
            local AttackType = SkillInfo[4]
            local AttackDistance = SkillInfo[5]
            local SkipFirst = SkillInfo.SkipFirst
            local FormatSkill = SkillInfo.FormatSkill
            local IncrementDistance = SkillInfo.IncrementD
            local AddCooldown = SkillInfo.AddCd
            local Rollback = SkillInfo.Rollback
            local BuiltAttackData = {}
            local AddedAttackDistance = 0
            local IsAttackTable = if type(AttackName) == "table" then true else false
            local IsCooldownTable = if type(AttackCooldown) == "table" then true else false
            local IsDistanceTable = if type(AttackDistance) == "table" then true else false

            for Count = 1, NumberOfAttacks do
                local StartingCount = Count
                local SkillName = if IsAttackTable then AttackName[Count] else AttackName
                local SkillCooldown = if IsCooldownTable then if #AttackCooldown == 1 then AttackCooldown[1] else AttackCooldown[Count] else AttackCooldown
                local SkillDistance = if IsDistanceTable then AttackDistance[Count] else AttackDistance

                if Rollback then
                    Count -= 1
                end

                if not IsAttackTable and NumberOfAttacks > 1 then
                    if Count <= 1 and SkipFirst then
                        if Rollback then
                            if Count == 0 then
                                Count = ""
                            end
                        else
                            Count = ""
                        end
                    end
                else
                    Count = ""
                end

                if typeof(SkillName) ~= "Instance" then
                    if not FormatSkill then
                        SkillName = SkillName..Count
                    else
                        SkillName = string.gsub(SkillName, "*", Count)
                    end
                end

                if IncrementDistance and StartingCount >= IncrementDistance[1] then
                    AddedAttackDistance += IncrementDistance[2]
                    SkillDistance += AddedAttackDistance
                end

                if AddCooldown and StartingCount >= AddCooldown[1] then
                    SkillCooldown += AddCooldown[2]
                end

                table.insert(TargetTable[TargetIndex].Skills, {Skill = SkillName, Cooldown = SkillCooldown, Type = AttackType, Distance = SkillDistance})
            end
        end
        TargetTable[TargetIndex].SkillInfo = nil
    end

    return TargetTable[TargetIndex]
end

SetGlobal("get player pet")
local function GetPlayerPet()
    CheckForCharacter()
    local rPets = require(Pets)
    while not (KillSwitch or ScriptUnloaded) do
        local PetData = PlayerCharacter and PlayerCharacter:FindFirstChild("PetData")
        if PetData and PetSkills then
            task.wait(.5)
            local ItemName = PetData:GetAttribute("ItemName")
            if ItemName and string.find(tostring(ItemName), "Egg") then
                task.wait(1)
                continue
            end
            local PetName = ReplicatedStorage.PlayerEquips[PlayerName].Pet:FindFirstChild(ItemName)
            if not PetName then
                task.wait(1)
                continue
            end
            local PetRef = rPets:GetPetSkillFromPetRef(PetName)
            if not PetRef then
                task.wait(1)
                continue
            end
            return BuildAttackData(PetSkills, PetRef)
        end
        task.wait(1)
    end
end

SetGlobal("get player class")
local function GetPlayerClass()
    SV.PlayerClass = WaitForAttribute(LocalPlayer, "Class")
    if ConnectionTable.ClassConnection then
        DisconnectVariable("ClassConnection")
    end
    task.spawn(function()
        if SV.PlayerClass == "Summoner" then
            local OnCollected = Remotes:WaitForChild("Effect_SoulObject_OnCollected", math.huge)
            ConnectionTable["ClassConnection"] = OnCollected.OnClientEvent:Connect(function(a, b, GUID, d, e)
                OnCollected:FireServer(GUID)
            end)
        elseif SV.PlayerClass == "Necromancer" then
            local OnCollected = Remotes:WaitForChild("Effect_SoulObjectNecromancer_OnCollected", math.huge)
            ConnectionTable["ClassConnection"] = OnCollected.OnClientEvent:Connect(function(a, b, GUID, d, e)
                OnCollected:FireServer(GUID)
            end)
        elseif SV.PlayerClass == "Dragoon" then
            local EnemyMarked = Remotes:WaitForChild("Combat_EnemyMarked", math.huge)
            local LastCombo = 0
            ConnectionTable["ClassConnection"] = EnemyMarked.OnClientEvent:Connect(function(Marked, b, c, d)
                if time() < LastCombo then
                    return
                end
                Remotes:WaitForChild("Skillset_Dragoon_InfinityStrikeStart", math.huge):FireServer()
                task.wait(0.2)
                Remotes:WaitForChild("Skillset_Dragoon_InfinityStrike", math.huge):FireServer()
                task.wait(0.2)
                Remotes:WaitForChild("Skillset_Dragoon_MultiStrike", math.huge):FireServer()
                task.wait(0.2)
                Remotes:WaitForChild("Skillset_Dragoon_DragonSlam", math.huge):FireServer()
                LastCombo = time()+9
            end)
        elseif SV.PlayerClass == "Demon" then
            local LifeSteal = Remotes:WaitForChild("Skillset_Demon_LifeSteal", math.huge)
            while SV.PlayerClass == "Demon" do
                if KillSwitch then
                    break
                end
                repeat
                    task.wait()
                until CurrentMob
                LifeSteal:FireServer({CurrentMob, CurrentMob, CurrentMob})
                task.wait(8.1)
            end
        end
    end)
    if ClassSkills then
        if ClassSkills[SV.PlayerClass].Distance == "Ranged" then
            SV.IsRanged = true
        else
            SV.IsRanged = nil
        end

        return BuildAttackData(ClassSkills, SV.PlayerClass)
    else
        SaveErrorToFile("PLAYER CLASS", "Unable to identify players class. Attack data does not exist.", SV.PlayerClass)
    end
end

SetGlobal("build shop values")
local function BuildShopValues(TargetDropdown, TargetShop)
    if type(TargetShop) == "table" then
        local ShopDisplay = {}
        local ShopReal = {}
        for Index, Data in TargetShop do
            local DisplayName = Data.VisualName.." (" .. FormatNumber(Data.CoinPrice) .. ", " ..Data.CurrencyType.. ")"
            table.insert(ShopDisplay, DisplayName)
            ShopReal[DisplayName] = { InternalName = Data.InternalName, VisualName = Data.VisualName, CoinPrice = Data.CoinPrice, CurrencyType = Data.CurrencyType}
        end
        table.sort(ShopDisplay, function(a, b)
            return ShopReal[a].CoinPrice < ShopReal[b].CoinPrice
        end)

        Options[TargetDropdown]:SetValues(ShopDisplay)
        return ShopReal
    end
    local rItems
    if SV.CanRequire then
        rItems = require(Items)
    end
    local FoundShopName = TargetShop
    local FoundShop = Shop.LocalShops:FindFirstChild(TargetShop) or nil
    if not FoundShop then
        warn("Shop \"" ..TargetShop.. "\" does not exist")
        return
    end

    local CurrencyItem = FoundShop:FindFirstChild("CurrencyItem") or nil
    if not CurrencyItem then
        warn("Could not find currency for shop \"" ..TargetShop.. "\"")
    end

    FoundShop = FoundShop:FindFirstChild("Items") or nil
    if not FoundShop then
        warn("Could not find items for \"" ..TargetShop.. "\"")
        return
    end

    local ShopDisplay = {}
    local ShopReal = {}
    for Index, Item in FoundShop:GetChildren() do
        local ItemPrice = Item.AskingPrice.Value
        local ItemName
        if rItems then
            ItemName = rItems[Item.Name].DisplayKey
        else
            ItemName = Item.Name
        end
        if #ItemName > 20 then
            ItemName = string.sub(ItemName, 1, 20):gsub("%s+$", "") .. "..."
        end
        local DisplayName = ItemName.." (" .. FormatNumber(ItemPrice) .. ")"
        table.insert(ShopDisplay, DisplayName)
        ShopReal[DisplayName] = { InternalName = Item.Name, VisualName = ItemName, CoinPrice = ItemPrice }
    end

    table.sort(ShopDisplay, function(a, b)
        return ShopReal[a].CoinPrice < ShopReal[b].CoinPrice
    end)

    ShopReal.ShopInfo = { ShopName = FoundShopName, Currency = CurrencyItem.Value }

    Options[TargetDropdown]:SetValues(ShopDisplay)
    return ShopReal
end

SetGlobal("mass item sell")
local function RecycleFromInventory(Method, SelectedItems)
    local HexesToSave = {}
    local AddHexes = Options.SaveUserHexesInput.Value
    if AddHexes then
        if AddHexes ~= "" and AddHexes ~= " " then
            local StandardizeCommas = string.gsub(AddHexes, ", ", ",")
            local RemoveHashTags = string.gsub(StandardizeCommas, "#", "")
            local SplitHexes = string.split(RemoveHashTags, ",")
            for Index, Hex in SplitHexes do
                if Hex ~= "" and Hex ~= " " then
                    table.insert(HexesToSave, string.lower(Hex))
                end
            end
        end
        for Index, Hex in SV.SpecialHexColors do
            table.insert(HexesToSave, Hex)
        end
    end

    local ItemsToRecycle = {}
    for ItemName, GroupedData in SV.RealCosmeticTable do
        if SelectedItems[ItemName] then
            for Index, ItemData in GroupedData do
                local CheckDye = ItemData.Dye
                if CheckDye then
                    local GoodDye
                    for Index, Dye in HexesToSave do
                        if string.match(CheckDye, "^"..Dye) then
                            GoodDye = true
                            break
                        end
                    end
                    if not GoodDye then
                        table.insert(ItemsToRecycle, {
                            UUID = ItemData.UUID,
                            Name = ItemData.Name
                        })
                        GroupedData[Index] = nil
                    end
                else
                    table.insert(ItemsToRecycle, {
                        UUID = ItemData.UUID,
                        Name = ItemData.Name
                    })
                    GroupedData[Index] = nil
                end
            end
        end
    end

    if Method == "Recycle" then
        Library:Notify("Attempting to recycle " ..tostring(#ItemsToRecycle).. " items", 5)
        Remotes:WaitForChild("Recycler_Recycle", math.huge):FireServer(ItemsToRecycle)
    elseif Method == "Gold" then
        Library:Notify("Attempting to sell " ..tostring(#ItemsToRecycle).. " items", 5)
        Remotes:WaitForChild("Drops_SellItems", math.huge):InvokeServer(ItemsToRecycle)
    end
end

SetGlobal("item sell check")
local function ItemSellCheck(NewItem, ManualSell) -- only called NewItem because I didn't want to change it all
    local IsDebug = ISV.Debug
    local Success, Result = pcall(function()
        SellItemCheck = SellItemCheck + 1
        if IsDebug then
            print(string.format(
                "Sending item %s through sell process",
                NewItem and NewItem.Name or "[UNABLE TO GET NAME, ITEM DOES NOT EXIST?]"
            ))
        end

        if SV.CanRequire then
            if not SV.Charms then
                SV.Charms = require(Charms:WaitForChild("Charms"))
            end
            if not SV.Items then
                SV.Items = require(Items)
            end
        end

        if EquipInProgress ~= 0 then
            repeat task.wait() until EquipInProgress == 0
            if not NewItem or not NewItem.Parent or not NewItem.Parent.Name then
                SellItemCheck = SellItemCheck - 1
                return
            end
            if NewItem.Parent.Name ~= "Items" then
                SellItemCheck = SellItemCheck - 1
                return
            end
        end

        local Count = NewItem:FindFirstChild("Count")
        local Locked = NewItem:FindFirstChild("Locked")
        local Favorited = NewItem:FindFirstChild("Favorited")
        local GiftWrap = NewItem:FindFirstChild("GiftWrap")
        if Count or Locked or Favorited or GiftWrap then
            if IsDebug then
                print(string.format(
                    "JDRS: Didn't sell %*, %*",
                    NewItem, Count or Locked or Favorited or GiftWrap
                ))
            end
            SellItemCheck = SellItemCheck - 1
            return
        end

        if not NewItem or not NewItem.Name then
            if IsDebug then
                print("JDRS: item had no name")
            end
            SellItemCheck = SellItemCheck - 1
            return
        end

        local NewItemName = tostring(NewItem.Name)
        local XP  = NewItem:FindFirstChild("XP") or string.find(NewItemName, "Pet")
        if XP and not SV.IncludePets then
            if IsDebug then
                print(string.format(
                    "JDRS: didn't sell %*, pet",
                    NewItem
                ))
            end
            SellItemCheck = SellItemCheck - 1
            return
        end

        local IsCharm
        if SV.Charms and SV.Charms[NewItem.Name] then
            IsCharm = true
            if not SV.IncludeCharms then
                if IsDebug then
                    print(string.format(
                        "JDRS: didn't sell %*, charm",
                        NewItem
                    ))
                end
                SellItemCheck = SellItemCheck - 1
                return
            end
        end

        local KeepItem = false
        local ItemRarity, AmountOfPerks = GetRarity(NewItem)
        if not IsCharm and tostring(ItemRarity) ~= "NotEquipment" then
            if ItemRarity == 7 then
                if IsDebug then
                    print(string.format(
                        "JDRS: didn't sell %*, Zero Gear",
                        NewItem
                    ))
                end
                return
            elseif not KeepTier then
                SellItem(NewItem, string.format(
                    "Selling %* because no tier is selected to be saved (%*)",
                    NewItem, KeepTier
                ))
                return
            elseif ItemRarity < KeepTier then
                SellItem(NewItem, string.format(
                    "Selling %* because it is tier %* and tier %* or above is selected",
                    NewItem, ItemRarity, KeepTier
                ))
                return
            end
            KeepItem = true
        end

        if SV.SellTowerEggs and IsTowerEgg(NewItem) then
            SellItem(NewItem, string.format(
                "Selling %* because it is listed as a tower egg",
                NewItem
            ))
            return
        end

        local Egg = table.find(SV.EggList, NewItemName) or false
        local SavedPerkName = false
        local SavedPerkValue = false
        local FoundPerfectPerk = false
        local ItemPerks = {}
        if not Egg and AmountOfPerks and AmountOfPerks > 0 then
            if SV.KeepPerks and SV.SelectedPerks then
                for PerkNumber = 1, AmountOfPerks do
                    if FoundPerfectPerk then break end
                    local PerkString = "Perk" ..tostring(PerkNumber)
                    local PerkName = NewItem:WaitForChild(PerkString, 10)
                    if PerkName then
                        repeat 
                            task.wait()
                        until PerkName.Value and PerkName.Value ~= ""
                        local PerkValue = PerkName:WaitForChild("PerkValue", 10)
                        if PerkValue then
                            repeat 
                                task.wait()
                            until PerkValue.Value and PerkValue.Value ~= ""
                            PerkValue = FormatDecimal(PerkValue.Value)
                            if IsDebug then
                                table.insert(ItemPerks, string.sub(PerkName.Value, 1, 7) .. ": " ..PerkValue)
                            end

                            local IsSelectedPerk = SV.SelectedPerks[PerkName.Value]
                            if IsSelectedPerk then
                                local PerkPercentage = IsSelectedPerk.PerkValue
                                local PetPerkPercentage = IsSelectedPerk.PetPerkValue or nil
                                if IsSelectedPerk.LowerMax then
                                    PerkPercentage = FormatDecimal(PerkPercentage + OffsetMax)
                                    if PetPerkPercentage then
                                        PetPerkPercentage = FormatDecimal(PetPerkPercentage + OffsetMax)
                                    else
                                        PetPerkPercentage = PerkPercentage
                                    end
                                else
                                    PerkPercentage = FormatDecimal(PerkPercentage - OffsetMax)
                                    if PetPerkPercentage then
                                        PetPerkPercentage = FormatDecimal(PetPerkPercentage - OffsetMax)
                                    else
                                        PetPerkPercentage = PerkPercentage
                                    end
                                end

                                --print(IsSelectedPerk.PerkName, PerkName.Value, PerkName.Value == IsSelectedPerk.PerkName, PerkValue, PerkPercentage, PerkValue >= PerkPercentage)
                                local PerkMatches = (not IsSelectedPerk.LowerMax and PerkValue >= PerkPercentage) or (IsSelectedPerk.LowerMax and PerkValue <= PerkPercentage)
                                local PetPerkMatches = (XP or IsCharm) and (not IsSelectedPerk.LowerMax and PerkValue >= PetPerkPercentage) or (IsSelectedPerk.LowerMax and PerkValue <= PetPerkPercentage)
                                if PerkMatches or PetPerkMatches then
                                    SavedPerkName = IsSelectedPerk.VisualName
                                    SavedPerkValue = math.round(PerkValue * 100)
                                    FoundPerfectPerk = true
                                    KeepItem = true
                                    break
                                else
                                    KeepItem = nil
                                end
                            else
                                KeepItem = nil
                            end
                        end
                    else
                        SaveErrorToFile("UNABLE TO FIND PERK", string.format(
                            "Waiting for perk #%d exceeded maximum allowed time of 10 seconds, does %s, have %d perks?",
                            PerkNumber, NewItemName, AmountOfPerks
                        ), string.format(
                            "Item is tier %d and was flagged as having %d perks",
                            ItemRarity, AmountOfPerks
                        ))
                    end
                end
            end
        end

        if not (Egg or KeepItem or FoundPerfectPerk) then
            SellItem(NewItem, string.format(
                "Selling %*, %*",
                NewItem, ItemPerks and #ItemPerks > 0 and table.concat(ItemPerks, ", ") or "item type not defined in script"
            ))
            return
        else
            if not ManualSell then
                Library:Notify("<font color='#80FF80'>Kept item:</font> " ..NewItemName, 1)
            end
            SellItemCheck = SellItemCheck - 1
        end

        if ManualSell then
            return
        end

        Egg = table.find({ "AetherEgg", "CupidEgg", "SkeletonEgg", "SantaEgg" }, NewItemName) or false
        if Egg or FoundPerfectPerk and SV.DiscordWebhookLink and SV.PerkPing then
            local Message
            if Egg then
                Message = "Kept item **" ..NewItemName.. "**! " ..DiscordPingType
            elseif FoundPerfectPerk then
                Message = "Kept **" ..NewItemName.. "** because **" ..tostring(SavedPerkName).. " " ..tostring(SavedPerkValue).. "%** was found!" ..DiscordPingType
            end
            pcall(function()
                local MessageContent = {
                    ["username"] = "Drop Logger",
                    ["content"] = Message
                }
                RequestMessage(SV.DiscordWebhookLink, MessageContent, false)
            end)
            return
        end
    end)
    if not Success then
        local ExtraMessage
        if not SV then
            ExtraMessage = "script unloaded before an item could be sold"
        end
        SaveErrorToFile("FAILURE TO SELL ITEM", Result, ExtraMessage)
    end
end

SetGlobal("check score")
local function GetLeaderboardScore(Leaderboard, TotalLabel, DailyLabel, TotalAllowed, DailyAllowed, EventBoss)
    local SelectedLeaderboard = tostring(Leaderboard)
    if EventBoss then
        local Date = os.date("*t")
        local Year = Date["year"]
        SelectedLeaderboard = SelectedLeaderboard.. tostring(Year)
    end

    local GetScore = Remotes:WaitForChild("LeaderboardHookup_GetScore", math.huge)
    LeaderboardData = GetScore:InvokeServer(SelectedLeaderboard, 1)
    if not LeaderboardData then
        LeaderboardData = GetScore:InvokeServer(SelectedLeaderboard, 5)
    end

    if not LeaderboardData then
        TotalLabel:SetText("Total: NO DATA")
        DailyLabel:SetText("Daily: NO DATA")
        return
    end
    local TotalScore = tonumber(LeaderboardData[1])
    local DailyScore = tonumber(LeaderboardData[2])

    TotalLabel:SetText("Total: " ..FormatNumber(TotalScore))
    DailyLabel:SetText("Daily: " ..FormatNumber(DailyScore))

    if (TotalAllowed and TotalScore and TotalScore >= TotalAllowed) or (DailyAllowed and DailyScore and DailyScore >= DailyAllowed) then
        Library:Notify("Limit reached, if you update the limit please restart the dungeon to continue.")
        return true
    end
end

SetGlobal("create toggles")
local function CreateToggles(ToggleTable)
    for Index, Data in ToggleTable do
        local FunctionValue = Data.FunctionValue or nil
        local DataTable = {
            Text = Data.Text,
            Default = if Data.Button then nil else false,
            Tooltip = Data.Tooltip or nil
        }

        if Data.AttachedFunction then
            if not Data.Button then
                DataTable.Callback = function(ChangedValue)
                    Data.AttachedFunction(ChangedValue, FunctionValue)
                end
            else
                DataTable.Func = function(ChangedValue)
                    Data.AttachedFunction(FunctionValue, ChangedValue)
                end
            end
        end

        if not Data.Button then
            Data.Tab:AddToggle(tostring(Data[1]), DataTable)
        else
            Data.Tab:AddButton(DataTable)
        end
    end
end

SetGlobal("getting obsidian Library")
if SV.BadExecutor then
    Library = SaveScriptToFiles("https://raw.githubusercontent.com/justdoingrandomstuff/old_obsidian_library/main/old_library", "L", 1)
else
    Library = SaveScriptToFiles("https://raw.githubusercontent.com/deividcomsono/Obsidian/main/Library.lua", "L", 1)
end

Options = Library.Options
Toggles = Library.Toggles

SetGlobal("creating window")
local Window = Library:CreateWindow({
    Title = "World Zero",
    Footer = "Script made by: justdoingrandomstuff",
    Icon = 17210785932,
    NotifySide = "Right",
    AutoShow = true,
    ShowCustomCursor = false,
    ToggleKeybind = Enum.KeyCode.Zero,
    EnableCompacting = true
})
Window:SetCornerRadius(20)

if not SV.GeneralTab then -- for unloaded general tab
SetGlobal("creating general tab")
local GenTab = Window:AddTab({
    Name = "General",
    Icon = "rbxassetid://9671045892"
})
if IsMainMenu or IsWorld then
    GenTab:UpdateWarningBox({
        Title = "Warning",
        Text = "Script functionality is heavily limited when outside of dungeons. Most functions have been entirely disabled for your safety.",
        IsNormal = false,
        Visible = true,
        LockSize = true
    })
end
local LeftTab = GenTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Main")
    local SecondTab = LeftTab:AddTab("Settings")
local RightTab = GenTab:AddRightTabbox("Right Tabbox")
    local ThirdTab = RightTab:AddTab("Extra")
    local FourthTab = RightTab:AddTab("Settings")

local function ToggleKillaura(ChangedValue)
    if ChangedValue then
        Toggles.KillauraToggle:SetDisabled(true)
        Toggles.KillauraToggle:SetText("<font color='#FF3333'>Killaura</font>")
    else
        Toggles.KillauraToggle:SetDisabled(false)
        Toggles.KillauraToggle:SetText("<font color='#ffffff'>Killaura</font>")
    end
end
local function ToggleSafeKillaura(ChangedValue)
    if ChangedValue then
        Toggles.SafeKillauraToggle:SetDisabled(true)
        Toggles.SafeKillauraToggle:SetText("<font color='#FF3333'>Safe killaura</font>")
    else
        Toggles.SafeKillauraToggle:SetDisabled(false)
        Toggles.SafeKillauraToggle:SetText("<font color='#ffffff'>Safe killaura</font>")
    end
end

CreateToggles({
    { "KillauraToggle", Text = "Killaura", Tab = FirstTab, AttachedFunction = ToggleSafeKillaura },
    { "SafeKillauraToggle", Text = "Safe killaura", Tab = FirstTab, AttachedFunction = ToggleKillaura },
    { "AutoProgressToggle", Text = "Autofarm", Tab = FirstTab },
    { "CollectDropToggle", Text = "Auto collect drops", Tab = ThirdTab },
    { "PetKillauraToggle", Text = "Pet killaura", Tooltip = "Vulnerable to getting detected by anticheat changes! Use at your own risk!", Tab = ThirdTab },
    { "RestartStuckToggle", Text = "Rejoin if stuck", Tooltip = "if you stop doing damage for a long enough period of time this toggle will assume you're stuck and attempt to restart the dungeon.", Tab = ThirdTab },
    { "DodgeLethalToggle", Text = "Dodge lethal damage", Tooltip = "Melee classes only. Some attacks may automatically be dodged even when turned off.", Tab = ThirdTab },
    { "AutoPrestigeToggle", Text = "Auto prestige", Tooltip = "When you reach level 160 the script will teleport you to world 1, prestige, and then go to crabby crusade.", Tab = ThirdTab }
})
SecondTab:AddLabel("Account for ping", true)
SecondTab:AddSlider("PingSlider", {
    Text = "Ping",
    Suffix = "%",
    Default = 100,
    Min = 0,
    Max = 200,
    Rounding = 0,
    Compact = true,
    Tooltip = "Adds delay to when each attack is used based off your ping. May help reduce kicks.\nDOES NOT APPLY TO SAFE KILLAURA",
    Callback = function(ChangedValue)
        PingMultiplier = ChangedValue / 100
    end
})
SecondTab:AddLabel("Killaura attack delay", true)
SecondTab:AddSlider("AttackDelaySlider", {
    Text = "Seconds",
    Default = 0,
    Min = 0,
    Max = 2,
    Rounding = 2,
    Compact = true,
    Tooltip = "Adds delay to when each attack is used.\nDOES NOT APPLY TO SAFE KILLAURA",
    Callback = function(ChangedValue)
        AddedDelay = ChangedValue
    end
})
SecondTab:AddLabel("Delay between attacks", true)
SecondTab:AddSlider("DelayAttackSlider", {
    Text = "Seconds",
    Default = 0,
    Min = 0,
    Max = 0.5,
    Rounding = 2,
    Compact = true,
    Tooltip = "When time is added the script will wait that long between performing attacks. When fighting bosses this setting is ignored completely.",
    Callback = function(ChangedValue)
        if ChangedValue == 0 then
            DelayAttacks = false
        else
            DelayAttacks = ChangedValue
        end
    end
})
SecondTab:AddLabel("Mob teleport rotation speed", true)
SecondTab:AddSlider("MobRotationSpeedSliderNew", {
    Text = "Studs",
    Default = 20,
    Min = 0,
    Max = 100,
    Rounding = 0,
    Compact = true,
    Tooltip = "Controls how fast your character rotates around mobs when teleporting to them. If you set it too fast and you're using a melee class then the script may not be able to do damage to mobs effectively.",
    Callback = function(ChangedValue)
        MobRotationSpeed = ChangedValue
    end
})
FourthTab:AddLabel("Pet killaura attack delay", true)
FourthTab:AddSlider("DelayPetAttackSlider", {
    Text = "Seconds",
    Default = 0,
    Min = 0,
    Max = 2,
    Rounding = 2,
    Compact = true,
    Tooltip = "Controls the delay between pet attacks when using the `Pet killaura` toggle",
    Callback = function(ChangedValue)
        if ChangedValue == 0 then
            DelayPetAttacks = false
        else
            DelayPetAttacks = ChangedValue
        end
    end
})
FourthTab:AddLabel("Rejoin on error delay", true)
FourthTab:AddSlider("RestartStuckSlider", {
    Text = "Seconds",
    Default = StuckDelay,
    Min = 30,
    Max = 120,
    Rounding = 0,
    Compact = true,
    Tooltip = "Controls how long it takes for the script to rejoin the dungeon when something in the dungeon or script has broken causing you to be unable to complete it.",
    Callback = function(ChangedValue)
        StuckDelay = ChangedValue
    end
})
end -- for unloaded general tab

if not SV.EventTab then -- for unloaded event tab
SetGlobal("event tab")
local EventTabIconTable = {
    [1] = "rbxassetid://8202463897",
    [2] = "rbxassetid://8723477744",
    [3] = "rbxassetid://8723477744",
    [4] = "rbxassetid://9299343400",
    [5] = "rbxassetid://9299343400",
    [6] = "rbxassetid://11582306327",
    [7] = "rbxassetid://11582306327",
    [8] = "rbxassetid://124707423544340",
    [9] = "rbxassetid://124707423544340",
    [10] = "rbxassetid://5763863934",
    [11] = "rbxassetid://81638085579862",
    [12] = "rbxassetid://8202463897"
}
local EventTab = Window:AddTab({
    Name = "Events",
    Icon = EventTabIconTable[os.date("*t").month]
})
local LeftTab = EventTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Boss fight")
    local SecondTab = LeftTab:AddTab("Advanced")
local RightTab = EventTab:AddRightTabbox("Right Tabbox")
    local ThirdTab = RightTab:AddTab("Wheel")
    local FourthTab = RightTab:AddTab("Battlepass")
    local FifthTab = RightTab:AddTab("Extra")

FirstTab:AddToggle("CollectBuffToggle", {
    Text = "Collect selected buffs",
    Default = false,
    Tooltip = "Pick buffs from the dropdown menu below that the script will pick up"
})
FirstTab:AddDropdown("OrbBuffDropdown", {
    Values = {
        DamageBuffOrb = "Damage Boost",
        UltChargeBuffOrb = "Ultimate",
        HealthBuffOrb = "Healing",
        DefenseBuffOrb = "Shield"
    },
    Multi = true,
    AllowNull = true,
    Default = "",
    MaxVisibleDropdownItems = 5,
    Searchable = true,
    Callback = function(ChangedValue)
        if IsDungeon and Options.OrbBuffDropdown:GetActiveValues(true) > 0 then
            SV.SelectedOrbs = ChangedValue
        else
            SV.SelectedOrbs = nil
        end
    end
})
local TotalLabel, TotalAllowed
local DailyLabel, DailyAllowed
SecondTab:AddDropdown("EventBossDropdown", {
    Values = {
        CUPID_KILLS_ = "Cupid",
        EASTERBUNNY_KILLS_ = "Easter Bunny",
        KRAKEN_KILLS_ = "Kraken",
        VANE_KILLS_ = "Vane",
        FALLENKING_KILLS_ = "Fallen King",
        SANTA_KILLS_ = "Korrupted Klaus"
    },
    Multi = false,
    AllowNull = false,
    Default = "",
    Text = "Select event boss",
    Searchable = true,
    Callback = function(ChangedValue)
        if IsWorld or IsDungeon and ChangedValue then
            task.wait(1)
            if GetLeaderboardScore(ChangedValue, TotalLabel, DailyLabel, TotalAllowed, DailyAllowed, true) then
                Library:Notify("Event boss clear limit reached.", 999999999)
                local TempStop = true
                local CanTarget = false
            end
        end
    end
})
TotalLabel = SecondTab:AddLabel("Total: ?", false)
SecondTab:AddInput("TotalEventInput", {
    Text = "Stop after X total kills",
    Default = "",
    Placeholder = "number here",
    Callback = function(ChangedValue)
        if IsDungeon then
            TotalAllowed = ChangedValue
        end
    end
})
    SecondTab:AddDivider({Margin = -5})
DailyLabel = SecondTab:AddLabel("Daily: ?", false)
SecondTab:AddInput("DailyEventInput", {
    Text = "Stop after X daily kills",
    Default = "",
    Placeholder = "number here",
    Callback = function(ChangedValue)
        if IsDungeon then
            DailyAllowed = ChangedValue
        end
    end
})
local CoinSpinLabel = ThirdTab:AddLabel("Coin cost: 5", true)
local SpinCount = 0
ThirdTab:AddInput("WheelSpinInput", {
    Text = "Wheel spin amount",
    Default = 1,
    Placeholder = "1",
    Tooltip = "If you enter more spins than you have in coins then the script will spin the wheel as many times as possible",
    Callback = function(ChangedValue)
        if typeof(ChangedValue) == "number" then
            CoinSpinLabel:SetText("Coin cost: " ..FormatNumber(ChangedValue*5))
            SpinCount = ChangedValue
        else
            SpinCount = 0
            CoinSpinLabel:SetText("Coin cost: <font color=\"rgb(255, 0, 0)\">invalid number</font>")
        end
    end
})
ThirdTab:AddButton({
    Text = "Spin wheel",
    Tooltip = "High amounts of spins WILL cause lag. I cannot do anything about this.",
    DoubleClick = true,
    Func = function()
        local JoinQueue = Remotes:FindFirstChild("EventSpinner_JoinQueue")
        for Spin = 1, SpinCount do
            JoinQueue:FireServer(LocalPlayer)
            task.wait()
        end
    end
})
    ThirdTab:AddDivider({Margin = -5})
local RecyclingItems
ThirdTab:AddButton({
    Text = "Recycle wheel items",
    Tooltip = "recycles all wheel items that are not locked or have a special hex\n\n<font color=\"rgb(255, 0, 0)\">you WILL crash if you have a lot of items, but they should be recycled when you rejoin</font>",
    DoubleClick = true,
    Func = function()
        if IsMainMenu or RecyclingItems then
            return
        end
        RecyclingItems = true
        if not SV.CanRequire then
            Library:Notify("Your executor doesn't support this option. Lacks require()", 5)
            return
        end

        local Profile_GetCosmetics = Remotes.Profile_GetCosmetics:InvokeServer()
        local rItems = require(Items)
        local ItemTable = {}
        local RealItemTable = {}
        local ScannedItems = {}
        local SelectedItems = {}

        -- create the table to look up items by their id's
        for Index, Item in SV.WheelItems do
            local ItemData = rItems[Item]
            if ItemData then
                ItemTable[ItemData.ID] = {
                    VisualName = tostring(ItemData.DisplayKey),
                    InternalName = tostring(Item)
                }
                SelectedItems[ItemData.DisplayKey] = true
            end
        end

        for Index, ItemData in Profile_GetCosmetics do
            if ItemData.lock or ItemData.fav then
                continue
            end
            local ItemRef = ItemTable[ItemData.id]
            if not ItemRef then
                continue
            end
            local VisualName = ItemRef.VisualName
            if not ScannedItems[VisualName] then
                ScannedItems[VisualName] = true
                RealItemTable[VisualName] = {}
            end
            if not ItemData.d then
                table.insert(RealItemTable[VisualName], {
                    UUID = ItemData.uuid,
                    Name = ItemRef.InternalName
                })
            else
                table.insert(RealItemTable[VisualName], {
                    UUID = ItemData.uuid,
                    Name = ItemRef.InternalName,
                    Dye = Color3.new(ItemData.d.r, ItemData.d.g, ItemData.d.b):ToHex()
                })
            end
        end

        SV.RealCosmeticTable = RealItemTable
        RecycleFromInventory("Recycle", SelectedItems)
        RecyclingItems = nil
    end
})
FourthTab:AddToggle("AutoClaimBattlepass", {
    Text = "Auto claim battlepass",
    Default = false,
    Tooltip = "Only works the first time it's turned on, if you gain a rank you will need to wait for the next teleport or toggle it off and on again before it attempts to claim rewards again"
})
do
    local Success, Result = pcall(function()
        if EF.Desync and EF.RaknetFunction and EF.RaknetFunction.is_enabled() then
            FifthTab:AddLabel("Can invisibly teleport: <font color='#33ff33'>Yes</font>", false)
        else
            FifthTab:AddLabel("Can invisibly teleport: <font color='#ff3333'>No</font>", false)
        end
    end)
    if not Success then
        FifthTab:AddLabel("Can invisibly teleport: <font color='#ff3333'>error</font>", false)
    end
end
    FifthTab:AddDivider({Margin = -5})
local FindingHidden
local DailyESP
FifthTab:AddLabel("Daily rewards", false)
FifthTab:AddButton({
    Text = "Teleport",
    Tooltip = "Teleports you to all of the daily rewards in the event hub such as the Obby end, Daily reward, and 3 hidden objects.\nIf you cannot invisibly teleport then you are blatantly teleported to all of them",
    Func = function()
        local Success, Result = pcall(function()
            if FindingHidden or IsMainMenu then
                return
            end
            local EventFinderReward = Workspace:FindFirstChild("EventFinderReward", true)
            if not EventFinderReward then
                Library:Notify("Go to the event hub if it is available.", 5)
                return
            end
            FindingHidden = true
            CheckForCharacter()
            local DailiesToTeleportTo = {}

            if EventFinderReward then
                for Index, Object in EventFinderReward.Models:GetChildren() do
                    table.insert(DailiesToTeleportTo, Object.PrimaryPart)
                end
            end

            local EventObbyReward = Workspace:FindFirstChild("EventObbyReward", true)
            if EventObbyReward then
                table.insert(DailiesToTeleportTo, EventObbyReward.Base)
            end
            
            local EventDailyReward = Workspace:FindFirstChild("EventDailyReward", true)
            if EventDailyReward then
                table.insert(DailiesToTeleportTo, EventDailyReward.Base)
            end
            
            if EF.Desync and EF.RaknetFunction.is_enabled() then
                EF.Desync(true)
                Remotes:WaitForChild("Health_Reset", math.huge):FireServer()
                task.wait(1)
                Remotes:WaitForChild("Health_Reset", math.huge):FireServer()
                LocalPlayer.CharacterAdded:Wait()
                task.wait(1)
            end

            Remotes:WaitForChild("SetMounted", math.huge):FireServer(true)
            task.wait(1)
            for Index, Object in DailiesToTeleportTo do
                PlayerRoot.CFrame = CFrame.new(Vector3.new(Object.Position.X, Object.Position.Y + (Object.Size.Y / 2), Object.Position.Z))
                task.wait(0.5)
            end

            local Spawn = Workspace:FindFirstChild("Spawn")
            local SpawnSize = Spawn.Size.Y / 2
            local SpawnPosition = Vector3.new(Spawn.Position.X, Spawn.Position.Y+SpawnSize, Spawn.Position.Z)
            PlayerRoot.CFrame = CFrame.new(SpawnPosition)
            task.wait(1)
            Remotes:WaitForChild("SetMounted", math.huge):FireServer(false)
            if EF.Desync and EF.RaknetFunction.is_enabled() then
                EF.Desync(false)
            end
            CollectCoins()
            FindingHidden = nil
        end)
        if not Success then
            SaveErrorToFile("TELEPORT DAILY REWARDS", Result)
        end
    end
}):AddButton({
    Text = "ESP",
    Tooltip = "Adds a highlight around all hidden daily rewards around an event hubs map if available.",
    Func = function()
        local EventFinderReward = Workspace:FindFirstChild("EventFinderReward", true)
        if not EventFinderReward then
            Library:Notify("Go to the event hub if it is available.", 5)
            return
        end
        if DailyESP then
            return
        end

        DailyESP = true
        local DailiesToESP = {}
        if EventFinderReward then
            for Index, Object in EventFinderReward.Models:GetChildren() do
                table.insert(DailiesToESP, Object)
            end
        end

        local EventObbyReward = Workspace:FindFirstChild("EventObbyReward", true)
        if EventObbyReward then
            table.insert(DailiesToESP, EventObbyReward.Base)
        end
        
        local EventDailyReward = Workspace:FindFirstChild("EventDailyReward", true)
        if EventDailyReward then
            table.insert(DailiesToESP, EventDailyReward.Base)
        end
        for i, o in DailiesToESP do
            if o.ClassName == "Model" then
                for Index, Descendant in o:GetDescendants() do
                    if Descendant.ClassName == "Highlight" and Descendant.Name ~= "ESP" then
                        Descendant:Destroy()
                        Descendant = nil
                        continue
                    end
                end
            end
            if not o:FindFirstChild("ESP") then
                local Highlight = Instance.new("Highlight")
                Highlight.FillTransparency = 0
                Highlight.Name = "ESP"
                Highlight.Parent = o
            else
                if o.ESP.Enabled then
                    o.ESP.Enabled = false
                else
                    o.ESP.Enabled = true
                end
            end
        end
        DailyESP = nil
    end
})
local TeleportingHoops
FifthTab:AddLabel("Claim flying hoops", false)
FifthTab:AddButton({
    Text = "Teleport hoops",
    Tooltip = "Teleports all the flying hoops on the map to your character and then returns them to their original position in an event hub if available.",
    Func = function()
        if TeleportingHoops or IsMainMenu then
            return
        end
        TeleportingHoops = 0
        CheckForCharacter()
        local Hoops = Workspace:FindFirstChild("Hoops")
        if Hoops then
            for Index, Hoop in Hoops:GetChildren() do
                TeleportingHoops = TeleportingHoops + 1
                task.spawn(function()
                    local PreviousPosition = Hoop:GetPivot()
                    Hoop:PivotTo(CFrame.new(PlayerRoot.Position))
                    task.wait(.1)
                    Hoop:PivotTo(PreviousPosition)
                    TeleportingHoops = TeleportingHoops - 1
                end)
            end
        else
            Library:Notify("Go to the event hub if it is available.", 5)
        end
        TeleportingHoops = nil
    end
})
local FindingEggs
local EggESP
FifthTab:AddLabel("Scavenger hunt", false)
FifthTab:AddButton({
    Text = "Teleport",
    Tooltip = "Blatantly teleports your character to all of the hidden scavenger hunt objects on the map if there is a scavenger hunt available in the world you are in.\nIf available to your executor the script will reset your character and then invisibly teleport you to all of the hidden objects.",
    Func = function()
        local Success, Result = pcall(function()
            if not IsWorld or FindingEggs then
                return
            end
            local ScavengerHunts = Workspace:FindFirstChild("ScavengerHunts")
            if not ScavengerHunts then return end
            local EggHunt = ScavengerHunts:FindFirstChild("EggHunt")
            if not EggHunt then return end
            local Spawns = EggHunt:FindFirstChild("Spawns")
            if not Spawns then return end
            FindingEggs = true
            CheckForCharacter()
            if EF.Desync and EF.RaknetFunction.is_enabled() then
                EF.Desync(true)
                Remotes:WaitForChild("Health_Reset", math.huge):FireServer()
                task.wait(1)
                Remotes:WaitForChild("Health_Reset", math.huge):FireServer()
                LocalPlayer.CharacterAdded:Wait()
                task.wait(1)
            end
            Remotes:WaitForChild("SetMounted", math.huge):FireServer(true)
            task.wait(1)
            for Index, EggSpawn in Spawns:GetChildren() do
                local EggPosition = Vector3.new(EggSpawn.Position.X, EggSpawn.Position.Y+GetPlayerSize(), EggSpawn.Position.Z)
                PlayerRoot.CFrame = CFrame.new(EggPosition)
                task.wait(.5)
            end
            local Spawn = Workspace:FindFirstChild("Spawn")
            if not Spawn then return end
            local SpawnSize = Spawn.Size.Y / 2
            local SpawnPosition = Vector3.new(Spawn.Position.X, Spawn.Position.Y+SpawnSize, Spawn.Position.Z)
            PlayerRoot.CFrame = CFrame.new(SpawnPosition)
            task.wait(1)
            Remotes:WaitForChild("SetMounted", math.huge):FireServer(false)
            if EF.Desync and EF.RaknetFunction.is_enabled() then
                EF.Desync(false)
            end
            CollectCoins()
            FindingEggs = nil
        end)
        if not Success then
            SaveErrorToFile("FIND ALL EGGS", Result)
        end
    end
}):AddButton({
    Text = "ESP",
    Tooltip = "Adds a highlight around all of the scavenger hunt objects if there is a scavenger hunt active in your current world.",
    Func = function()
        local Success, Result = pcall(function()
            if EggESP then return end
            local ScavengerHunts = Workspace:FindFirstChild("ScavengerHunts")
            if not ScavengerHunts then return end
            local EggHunt = ScavengerHunts:FindFirstChild("EggHunt")
            if not EggHunt then return end
            local HuntContainer = EggHunt:FindFirstChild("_ScavengerHuntContainer")
            if not HuntContainer then return end
            EggESP = true
            for i, o in HuntContainer:GetChildren() do
                local Highlight = o:FindFirstChild("ESP Highlight")
                if not Highlight then
                    local NewHighlight = Instance.new("Highlight")
                    NewHighlight.Name = "ESP Highlight"
                    NewHighlight.FillTransparency = 0
                    NewHighlight.Parent = o
                elseif Highlight then
                    if Highlight.Enabled then
                        Highlight.Enabled = false
                    else
                        Highlight.Enabled = true
                    end
                end
            end
            EggESP = nil
        end)
        if not Success then
            SaveErrorToFile("FIND ALL EGGS", Result)
        end
    end
})
end -- for unloaded event tab

if not SV.TradingTab then -- for unloaded trading tab
SetGlobal("trading tab")
local TradeTab = Window:AddTab({
    Name = "Trading",
    Icon = "rbxassetid://9671046601"
})
local LeftTab = TradeTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Player shop")
local RightTab = TradeTab:AddRightTabbox("Right Tabbox")
    local SecondTab = RightTab:AddTab("Trading")

FirstTab:AddToggle("PlacePlayerShopToggle", {
    Text = "Auto place player shop",
    Default = false,
    Tooltip = "Shop automatically gets removed if turned off",
    Callback = function(ChangedValue)
        if ChangedValue then
            local CheckForShopSpots = Workspace:FindFirstChild("ShopLocations")
            if CheckForShopSpots then
                for _, ShopSpots in CheckForShopSpots:GetChildren() do
                    if ShopSpots.PlayerOwner.Value == nil then
                        Remotes:WaitForChild("Shop_ClaimShop", math.huge):FireServer(ShopSpots)
                        Library:Notify("Placed shop!", 2)
                    end
                end
            end
        else
            Remotes:WaitForChild("Shop_StopShop", math.huge):FireServer()
        end
    end
})
FirstTab:AddDropdown("PlayerShopDropdown", {
    Values = {},
    Default = "",
    Multi = false,
    Text = "Open selected players shop",
    Callback = function(ChangedValue)
        if ChangedValue and IsWorld and SV.CanRequire then
            local rShop = require(Client.Gui):Get("Shop")
            rShop:Close()
            rShop:Open(Players[tostring(ChangedValue)])
        end
    end
})
FirstTab:AddButton({
    Text = "Scan for active player shops",
    Func = function()
        local ActivePlayerShops = {}
        local ShopLocations = Workspace:FindFirstChild("ShopLocations")
        if not ShopLocations then
            return
        end
        for Index, Descendant in ShopLocations:GetDescendants() do
            if Descendant:IsA("ObjectValue") then
                if Descendant.Name == "PlayerOwner" then
                    if Descendant.Value == PlayerName then
                        continue
                    end
                    table.insert(ActivePlayerShops, Descendant.Value)
                end
            end
        end
        Options.PlayerShopDropdown:SetValues(ActivePlayerShops)
    end
})
SecondTab:AddButton({
    Text = "Check trade for dupes",
    Func = function()
        if SV.CheckingTrade or IsMainMenu then
            return
        end

        SV.CheckingTrade = true

        local Success, Result = pcall(function()
            local pItems = ProfileInventory.Items
            local PlayerEquips = ReplicatedStorage.PlayerEquips:FindFirstChild(PlayerName)
            local CurrentTrade = nil
            local DupedItemCount = 0
            local ItemsToCheck = 0
            local StoredID = {}

            local function MarkItem(DupedItem)
                local NewFolder = Instance.new("Folder")
                    NewFolder.Name = "Explo".."ited"
                    NewFolder.Parent = DupedItem
                return
            end

            local function CheckForDupe(ItemToCheck)
                local ItemID = ItemToCheck.ID.Value
                for Index, CheckID in StoredID do
                    if CheckID.ID.Value == ItemToCheck.ID.Value then
                        MarkItem(CheckID)
                        Library:Notify("Found duped item: " ..CheckID.Name, 3)
                        DupedItemCount = DupedItemCount + 1
                        return
                    end
                end
                return
            end

            for Index, Trades in ReplicatedStorage:FindFirstChild("Trades"):GetChildren() do
                if Trades:FindFirstChild(PlayerName) then
                    CurrentTrade = Trades
                    break
                end
            end

            if not CurrentTrade then
                Library:Notify("You are not trading anyone", 3)
                SV.CheckingTrade = nil
                return
            end

            for Index, Players in CurrentTrade:GetChildren() do
                if Players.Name == LocalPlayer.Name then
                    continue
                end
                for Index, Descendant in Players:GetDescendants() do
                    if Descendant.Name == "ID" then
                        ItemsToCheck = ItemsToCheck + 1
                        table.insert(StoredID, Descendant.Parent)
                    end
                end
            end

            if ItemsToCheck == 0 then
                Library:Notify("No items to check", 3)
                SV.CheckingTrade = nil
                return
            end

            for Index, Descendant in pItems:GetDescendants() do
                if Descendant.Name =="ID" then
                    CheckForDupe(Descendant.Parent)
                end
            end

            for Index, Descendant in PlayerEquips:GetDescendants() do
                if Descendant.Name =="ID" then
                    CheckForDupe(Descendant.Parent)
                end
            end

            if DupedItemCount == 0 then
                Library:Notify("No duped items found", 3)
                SV.CheckingTrade = nil
                return
            end
        end)
        if not Success then
            SaveErrorToFile("SCAN TRADE FOR DUPE", Result)
        end
        SV.CheckingTrade = nil
    end
})
SecondTab:AddButton({
    Text = "Trade with last person",
    Func = function()
        if SV.PlayerBeingTraded ~= nil then
            local TradeAccept = Remotes:WaitForChild("Trade_Accept")
            TradeAccept:FireServer(Players[SV.PlayerBeingTraded])
            SendTrade()
        else
            Library:Notify("Last trade not found. Did YOU receive and accept a trade?", 5)
        end
    end
})
end -- for unloaded trading tab

if not SV.ClassesTab then -- for unloaded classes tab
SetGlobal("creating class tab")
local ClassTab = Window:AddTab({
    Name = "Classes",
    Icon = "rbxassetid://9671047048"
})
LeftTab = ClassTab:AddLeftTabbox("Left Tabbox")
    FirstTab = LeftTab:AddTab("Main")
RightTab = ClassTab:AddRightTabbox("Right Tabbox")
    SecondTab = RightTab:AddTab("Extra")

CreateToggles({
    { "GeneralClassBuffToggle", Text = "General class buffs", Tooltip = "Gives you Dual Wielders and Guardians buff", Tab = FirstTab },
    { "MoLBarrierToggle", Text = "MoL barrier", Tooltip = "Gives everyone else in the game a barrier instead of only yourself\nOnly Mage of Light can use this", Tab = SecondTab },
    { "DemonBloodBindingToggle", Text = "Demon Blood Binding", Tooltip = "Activates Demons Blood Binding skill that takes away health while boosting your own damage\nOnly Demon can use this", Tab = SecondTab },
    { "StormcallerSuperchargeToggle", Text = "Stormcaller Supercharge", Tooltip = "Activates Stormcallers Supercharge skill that takes away health while boosting your own damage and healing you a little when inflicting the Supercharge status\nOnly Stormcaller can use this", Tab = SecondTab },
})

local RangedClassLabel = FirstTab:AddLabel("Ranged class distance", false)
FirstTab:AddSlider("ChangedRangedXSlider", {
    Text = "X",
    Default = 25,
    Min = -100,
    Max = 100,
    Rounding = 0,
    Compact = true,
    Tooltip = "Forward and Backwards\nDefault is 20",
    Callback = function(ChangedValue)
        if Class and Class.Distance == "Ranged" then
            Xdistance = ChangedValue
        end
    end
})
FirstTab:AddSlider("ChangedRangedYSlider", {
    Text = "Y",
    Default = 55,
    Min = -100,
    Max = 100,
    Rounding = 0,
    Compact = true,
    Tooltip = "Up and Down\nDefault is 50",
    Callback = function(ChangedValue)
        if Class and Class.Distance == "Ranged" then
            Ydistance = ChangedValue
        end
    end
})
    FirstTab:AddDivider({Margin = -5})
local MeleeClassLabel = FirstTab:AddLabel("Melee class distance", false)
FirstTab:AddSlider("ChangedMeleeXSlider", {
    Text = "X",
    Default = 13,
    Min = -50,
    Max = 50,
    Rounding = 0,
    Compact = true,
    Tooltip = "Forward and Backwards\nDefault is 15",
    Callback = function(ChangedValue)
        if Class and Class.Distance == "Melee" then
            Xdistance = ChangedValue
        end
    end
})
FirstTab:AddSlider("ChangedMeleeYSlider", {
    Text = "Y",
    Default = 8,
    Min = -50,
    Max = 50,
    Rounding = 0,
    Compact = true,
    Tooltip = "Up and Down\nDefault is 8",
    Callback = function(ChangedValue)
        if Class and Class.Distance == "Melee" then
            Ydistance = ChangedValue
        end
    end
})
end -- for unloaded classes tab

if not SV.InventoryTab then -- for unloaded inventory tab
SetGlobal("creating inventory tab")
local InventoryTab = Window:AddTab({
    Name = "Inventory",
    Icon = "rbxassetid://9671046778"
})
local LeftTab = InventoryTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Inventory")
    local SecondTab = LeftTab:AddTab("Settings")
    local ThirdTab = LeftTab:AddTab("Equips")
local RightTab = InventoryTab:AddRightTabbox("Right Tabbox")
    local FourthTab = RightTab:AddTab("Cosmetics")
    local FifthTab = RightTab:AddTab("Hexes")

local function ToggleValue(ChangedValue, ToggleValue)
    if ChangedValue and not IsMainMenu then
        SV[tostring(ToggleValue)] = true
    else
        SV[tostring(ToggleValue)] = nil
    end
end

CreateToggles({
    { "AutoSellToggle", Text = "Auto sell items", Tooltip = "Only applies to new items. Eggs are not sold.", Tab = FirstTab },
    { "SellPetToggle", Text = "Sell pets", Tooltip = "Allow the auto sell functionalities to apply to pets as well", Tab = SecondTab, AttachedFunction = ToggleValue, FunctionValue = "IncludePets" },
    { "SellTowerEggToggle", Text = "Sell tower eggs", Tooltip = "Automatically sell eggs from towers if you are able to collect them", Tab = SecondTab, AttachedFunction = ToggleValue, FunctionValue = "SellTowerEggs" },
    { "SellCharmToggle", Text = "Sell tower eggs", Tooltip = "Automatically sell eggs from towers if you are able to collect them", Tab = SecondTab, AttachedFunction = ToggleValue, FunctionValue = "IncludeCharms" },
    { Button = true, Text = "Upgrade Primary", Tab = ThirdTab, AttachedFunction = UpgradeToMax, FunctionValue = "Primary" },
    { Button = true, Text = "Upgrade Offhand", Tab = ThirdTab, AttachedFunction = UpgradeToMax, FunctionValue = "Offhand" },
    { Button = true, Text = "Upgrade Armor", Tab = ThirdTab, AttachedFunction = UpgradeToMax, FunctionValue = "Armor" }
})
    FirstTab:AddDivider()
FirstTab:AddDropdown("AutoSellDropdown", {
    Values = {
        ["0"] = "none",
        ["3"] = "3-5",
        ["4"] = "4-5",
        ["5"] = "5"
    },
    Multi = false,
    Text = "Keep tiers",
    AllowNull = false,
    Default = "5",
    Callback = function(ChangedValue)
        ChangedValue = tonumber(ChangedValue)
        if ChangedValue and not IsMainMenu and ChangedValue > 0 then
            KeepTier = ChangedValue
        else
            KeepTier = nil
        end
    end
})
    FirstTab:AddDivider()
CreateToggles({
    { "KeepSelectedPerkToggle", Text = "Keep selected perks", Tooltip = "By default only S+ perks are kept", Tab = FirstTab, AttachedFunction = ToggleValue, FunctionValue = "KeepPerks" }
})
local SavePerkTable = {
    ["Gold Hoarder"] = { PerkValue = 0.2, PetPerkValue = 0.2, PerkName = "GoldDrop" },
    ["Lucky Looter"] = { PerkValue = 0.1, PetPerkValue = 0.1, PerkName = "PetFoodDrop" },
    ["Energized"] = { PerkValue = 0.15, PetPerkValue = 0.15, PerkName = "UltCharge" },
    ["HP UP"] = { PerkValue = 0.12, PetPerkValue = 0.07, PerkName = "BonusHP" },
    ["Attack Up"] = { PerkValue = 0.08, PetPerkValue = 0.05, PerkName = "BonusAttack" },
    ["Agility"] = { PerkValue = 0.1, PetPerkValue = 0.1, PerkName = "BonusWalkspeed" },
    ["Burn Resistance"] = { PerkValue = 0.9, PetPerkValue = 0.9, PerkName = "ResistBurn" },
    ["Poison Resistance"] = { PerkValue = 0.9, PetPerkValue = 0.9, PerkName = "ResistPoison" },
    ["Frost Resistance"] = { PerkValue = 0.9, PetPerkValue = 0.9, PerkName = "ResistFrost" },
    ["Knockdown Resistance"] = { PerkValue = 0.9, PetPerkValue = 0.9, PerkName = "ResistKockdown" },
    ["Untouchable"] = { PerkValue = 0.2, PerkName = "DodgeChance" },
    ["Rough Skin"] = { PerkValue = 0.1, PerkName = "RoughSkin" },
    ["Damage Reduction"] = { PerkValue = 0.08, PerkName = "DamageReduction" },
    ["Life Drain"] = { PerkValue = 0.06, PerkName = "LifeDrain" },
    ["Burn Chance"] = { PerkValue = 0.15, PerkName = "BurnChance" },
    ["Frost Chance"] = { PerkValue = 0.15, PerkName = "FrostChance" },
    ["Poison Chance"] = { PerkValue = 0.15, PerkName = "PoisonChance" },
    ["Crit Stack"] = { PerkValue = 0.15, PerkName = "CritStack" },
    ["Poisonous Thorns"] = { PerkValue = 0.6, PerkName = "PoisonThorns" },
    ["Elemental Resistance"] = { PerkValue = 0.4, PetPerkValue = 0.15, PerkName = "Elemental" },
    ["Ferocious"] = { PerkValue = 0.4, PetPerkValue = 0.15, PerkName = "Ferocious" },
    ["Vampiric"] = { PerkValue = 0.15, PetPerkValue = 0.05, PerkName = "Vampiric" },
    ["Boss Bane"] = { PerkValue = 0.3, PetPerkValue = 0.1, PerkName = "TestTier5" },
    ["Mob Slayer"] = { PerkValue = 0.3, PetPerkValue = 0.1, PerkName = "MobBoss" },
    ["Elite Assassin"] = { PerkValue = 0.3, PetPerkValue = 0.1, PerkName = "EliteBoss" },
    ["Opening Strike"] = { PerkValue = 0.25, PerkName = "OpeningStrike" },
    ["Self Destruct"] = { PerkValue = 0.5, PerkName = "Destruction" },
    ["Fortress"] = { PerkValue = 0.4, PerkName = "Fortress" },
    ["Glass"] = { PerkValue = 1, PerkName = "Glass" },
    ["Master Thief"] = { PerkValue = 0.35, PerkName = "MasterThief" },
    ["Oblivion"] = { PerkValue = 0.05, PetPerkValue = 0.05, PerkName = "Oblivion" },
    ["Reckless"] = { PerkValue = 0.25, PetPerkValue = 0.25, PerkName = "Reckless" },
    ["Comeback"] = { PerkValue = 0.3, PerkName = "Comeback" },
    ["Relentless"] = { PerkValue = 0.15, PerkName = "Relentless" },
    ["Duelist"] = { PerkValue = 0.3, PerkName = "Duelist" },
    ["Unstoppable"] = { PerkValue = 0.15, PerkName = "Unstoppable" },
    ["Survivor"] = { PerkValue = 0.2, PerkName = "Survivor" },
    ["Executioner"] = { PerkValue = 0.5, PetPerkValue = 0.5, PerkName = "Executioner" },
    ["Adrenaline"] = { PerkValue = 0.3, PerkName = "Adrenaline" },
    ["Cooldown Reduction"] = { PerkValue = 0.1, PerkName = "CooldownReduction" },
    ["Attack Speed"] = { PerkValue = 0.15, PerkName = "AttackSpeed" },
    ["Water Bubble"] = { PerkValue = 0.4, PerkName = "WaterBubble", LowerMax = true },
    ["Blessing"] = { PerkValue = 0.3, PerkName = "Blessing" },
    ["Deaths Door"] = { PerkValue = 0.5, PerkName = "DeathsDoor" },
    ["Protector"] = { PerkValue = 0.1, PerkName = "Protector" }
}
FirstTab:AddDropdown("PerkListDropdown", {
    Values = {},
    Text = "Perks to keep",
    Multi = true,
    AllowNull = true,
    Default = "",
    MaxVisibleDropdownItems = 5,
    Searchable = true,
    Callback = function(ChangedValue)
        if not IsMainMenu and Options.PerkListDropdown:GetActiveValues(true) > 0 then
            if not SV.SelectedPerks then
                SV.SelectedPerks = {}
            else
                table.clear(SV.SelectedPerks)
            end
            for Key in ChangedValue do
                local PerkData = SavePerkTable[Key]
                PerkData.VisualName = tostring(Key)
                SV.SelectedPerks[PerkData.PerkName] = PerkData
            end
        else
            if SV.SelectedPerks then
                table.clear(SV.SelectedPerks)
            end
        end
    end
})
local DropdownReference = {}
for Key in SavePerkTable do
    table.insert(DropdownReference, tostring(Key))
end
table.sort(DropdownReference, function(a,b)
    return a < b
end)
Options.PerkListDropdown:SetValues(DropdownReference)
FirstTab:AddButton({
    Text = "Sell inventory",
    DoubleClick = true,
    Tooltip = "all options including perk filtering are taken into account when selling your inventory",
    Func = function()
        local pItems = ProfileInventory:WaitForChild("Items")
        for Index, NewItem in pItems:GetChildren() do
            ItemSellCheck(NewItem, true)
        end
    end
})
SecondTab:AddLabel("Perfect perk offset", true)
SecondTab:AddSlider("PerkPercentSlider", {
    Text = "Offset",
    Default = 0,
    Min = 0,
    Max = 5,
    Rounding = 0,
    Compact = true,
    Tooltip = "Allows you to increase the range at which perks are kept. For example if you want Attack Up 7% and 8% then you would add 1 to the offset",
    Callback = function(ChangedValue)
        if not ChangedValue then
            ChangedValue = 0
        end
        OffsetMax = FormatDecimal(ChangedValue / 100)
    end
})
FourthTab:AddDropdown("CosmeticDropdown", {
    Values = {},
    Text = "Cosmetics",
    Multi = true,
    AllowNull = true,
    Default = "",
    MaxVisibleDropdownItems = 5,
    Searchable = true
})
FourthTab:AddButton({
    Text = "Clear selection",
    DoubleClick = true,
    Func = function()
        Options.CosmeticDropdown:SetValue(nil)
    end
})
FourthTab:AddButton({
    Text = "Scan cosmetics",
    Func = function()
        if IsDungeon or IsWorld then
            if not SV.CanRequire then
                Library:Notify("Your executor doesn't support this option. Lacks require()", 5)
                return
            end

            local Profile_GetCosmetics = Remotes.Profile_GetCosmetics:InvokeServer()
            local rItems = require(Items)
            local ItemTable = {}
            local VisualItemTable = {}
            local RealItemTable = {}
            local ScannedItems = {}

            -- create the table to look up items by their id's
            for Index, ItemData in rItems do
                if ItemData.Type == "Emote" or ItemData.Type == "Title" or ItemData.Type == "Furniture" or ItemData.Type == "Consumable" then
                    continue
                end
                ItemTable[ItemData.ID] = {
                    VisualName = tostring(ItemData.DisplayKey),
                    InternalName = tostring(Index)
                }
            end

            for Index, ItemData in Profile_GetCosmetics do
                if ItemData.lock or ItemData.fav then
                    continue
                end
                local ItemRef = ItemTable[ItemData.id]
                if not ItemRef then
                    continue
                end
                local VisualName = ItemRef.VisualName
                if not ScannedItems[VisualName] then
                    ScannedItems[VisualName] = true
                    RealItemTable[VisualName] = {}
                    table.insert(VisualItemTable, VisualName)
                end
                if not ItemData.d then
                    table.insert(RealItemTable[VisualName], {
                        UUID = ItemData.uuid,
                        Name = ItemRef.InternalName
                    })
                else
                    table.insert(RealItemTable[VisualName], {
                        UUID = ItemData.uuid,
                        Name = ItemRef.InternalName,
                        Dye = Color3.new(ItemData.d.r, ItemData.d.g, ItemData.d.b):ToHex()
                    })
                end
            end
            
            Options.CosmeticDropdown:SetValues(VisualItemTable)
            SV.RealCosmeticTable = RealItemTable
        end
    end
})
    FourthTab:AddDivider()
FourthTab:AddLabel("Pressing either of these buttons will either attempt to Recycle or Sell all the cosmetics you have selected above", true)
FourthTab:AddButton({
    Text = "Recycle",
    DoubleClick = true,
    Func = function()
        if IsDungeon or IsWorld then
            local SelectedItems = {}
            for Key in Options.CosmeticDropdown.Value do
                SelectedItems[Key] = true
            end
            RecycleFromInventory("Recycle", SelectedItems)
        end
    end
}):AddButton({
    Text = "Sell",
    DoubleClick = true,
    Func = function()
        if IsDungeon or IsWorld then
            local SelectedItems = {}
            for Key in Options.CosmeticDropdown.Value do
                SelectedItems[Key] = true
            end
            RecycleFromInventory("Gold", SelectedItems)
        end
    end
})
FifthTab:AddLabel("<font color='#FF3333'>ALL USER ENTERED HEXES MUST BE SEPARATED WITH COMMAS</font>\nAdding hexes example:\n<font color='#33FF33'>00ff00, a.a.b., [a-b].[1-2].e</font>", true)
    FifthTab:AddDivider()
local NumberOfEnteredHexes = FifthTab:AddLabel("Number of saved hexes: " ..FormatNumber(#SV.SpecialHexColors))
local UserEnteredHexes = FifthTab:AddLabel("Saved hexes:\nn/a\n+ (all special hexes)", true)
    FifthTab:AddDivider()
FifthTab:AddInput("SaveUserHexesInput", {
    Text = "Enter hexes to save",
    Default = "",
    ClearTextOnFocus = false,
    Placeholder = "hexes here",
    Callback = function(ChangedValue)
        if IsWorld or IsDungeon then
            ChangedValue = tostring(ChangedValue)
            ChangedValue = string.lower(ChangedValue)
            if ChangedValue == "" or ChangedValue == " " then
                NumberOfEnteredHexes:SetText("Number of saved hexes: " ..FormatNumber(#SV.SpecialHexColors))
                UserEnteredHexes:SetText("Saved hexes:\nn/a\n+ (all special hexes)")
                return
            end
            local StandardizeCommas = string.gsub(Options.SaveUserHexesInput.Value, ", ", ",")
            local RemoveHashTags = string.gsub(StandardizeCommas, "#", "")
            local SplitHexes = string.split(RemoveHashTags, ",")
            NumberOfEnteredHexes:SetText("Number of saved hexes: " ..FormatNumber(#SV.SpecialHexColors + #SplitHexes))
            UserEnteredHexes:SetText("Saved hexes:\n<font color='#33FF33'>" ..ChangedValue.. "</font>\n+ (all special hexes)")
            return
        end
    end
})
end -- for unloaded inventory tab

SetGlobal("creating dungeon tab")

if not SV.DungeonsTab then -- for unloaded classes tab
local DungeonTab = Window:AddTab({
    Name = "Dungeons",
    Icon = "rbxassetid://18739736091"
})
local LeftTab = DungeonTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Main")
    local SecondTab = LeftTab:AddTab("Settings")
local RightTab = DungeonTab:AddRightTabbox("Right Tabbox")
    local ThirdTab = RightTab:AddTab("Advanced\n(nightmare challenge)")

local function ToggleNightmare(ChangedValue, FunctionValue)
    if ChangedValue and IsDungeon then
        SV[tostring(FunctionValue)] = math.random(1005, 1007)
    else
        SV[tostring(FunctionValue)] = nil
    end
end

CreateToggles({
    { "ReplayMissionToggle", Text = "Auto restart mission", Tab = FirstTab },
    { "CollectChestToggle", Text = "Collect chests", Tab = FirstTab },
    { "HighestDungeonToggle", Text = "Do highest level dungeon", Tooltip = "Useful if you are leveling up as it moves to the highest level dungeon you're able to play and auto equips new gear if it's a higher level.", Tab = FirstTab },
    { "RandomNightmareDungeonToggle", Text = "Random nightmare dungeon", Tooltip = "Instead of replaying the current dungeon it will pick a random nightmare dungeon.", Tab = FirstTab, AttachedFunction = ToggleNightmare, FunctionValue = "RandomNightmareDungeon" },
    { "ReplayInfiniteTowerToggle", Text = "Limit infinite tower", Tooltip = "Allows you to restart infinite tower once a predetermined floor has been reached.", Tab = FirstTab }
})
SV.RestartDungeonDelay = 3
SecondTab:AddLabel("Restart dungeon delay", true)
SecondTab:AddSlider("ReplayMissionSlider", {
    Text = "Restart delay",
    Default = 3,
    Min = 1,
    Max = 60,
    Rounding = 0,
    Compact = true,
    Tooltip = "Changes the scripts delay when restarting the dungeon when `Auto restart mission` is selected.",
    Callback = function(ChangedValue)
        SV.RestartDungeonDelay = ChangedValue
    end
})
SV.CollectChestsDelay = 0.1
SecondTab:AddLabel("Collect chest delay", true)
SecondTab:AddSlider("ChestDelaySlider", {
    Text = "Collect chest delay",
    Default = 0.1,
    Min = 0.01,
    Max = 5,
    Rounding = 2,
    Compact = true,
    Tooltip = "Changes the scripts delay between chests being collected.",
    Callback = function(ChangedValue)
        SV.CollectChestsDelay = ChangedValue
    end
})
SecondTab:AddLabel("Infinite tower reset floor", true)
SecondTab:AddSlider("InfResetSlider", {
    Text = "Floor",
    Default = 200,
    Min = 155,
    Max = 400,
    Rounding = 0,
    Compact = true,
    Tooltip = "Allows you to change the floor that infinite tower restarts at when the `Periodically reset inf tower` option is selected.",
    Callback = function(ChangedValue)
        RestartAtFloor = ChangedValue
    end
})
SecondTab:AddLabel("Prioritize nightmare dungeons", true)
SecondTab:AddDropdown("PrioNmDropdown", {
    Values = {},
    Multi = true,
    AllowNull = true,
    Default = nil,
    MaxVisibleDropdownItems = 5,
    Searchable = true,
    Callback = function(ChangedValue)
        if not IsMainMenu and Options.PrioNmDropdown:GetActiveValues(true) > 0 then
            SV.PrioNmDCount = true
        else
            SV.PrioNmDCount = nil
        end
    end
})
SV.PrioritizedNightmareDungeons = {}
local NMDisplayValues = {}
for Index, Data in SV.DungeonListTable do
    if Data.Level > 0 and Data.Level < 175 then
        SV.PrioritizedNightmareDungeons[Data.DungeonName] = { ID = Data.DungeonID, Length = Data.DungeonDelay, SpecialPerk = Data.SpecialPerk or nil }
        table.insert(NMDisplayValues, Data.DungeonName)
    end
end
Options["PrioNmDropdown"]:SetValues(NMDisplayValues)
NMDisplayValues = nil
SV.TotalNightmareLabel = ThirdTab:AddLabel("Total nightmare clears: ?", false)
ThirdTab:AddInput("TotalNightmareInput", {
    Text = "Stop after X total clears",
    Default = "",
    Placeholder = "number here",
    Callback = function(ChangedValue)
        if IsDungeon then
            SV.StopAfterTotalNightmare = ChangedValue
        end
    end
})
    ThirdTab:AddDivider({Margin = -5})
SV.DailyNightmareLabel = ThirdTab:AddLabel("Daily nightmare clears: ?", false)
ThirdTab:AddInput("DailyNightmareInput", {
    Text = "Stop after X daily clears",
    Default = "",
    Placeholder = "number here",
    Callback = function(ChangedValue)
        if IsDungeon then
            SV.StopAfterDailyNightmare = ChangedValue
        end
    end
})
end -- for unloaded classes tab

if not SV.InventoryTab then
SetGlobal("equipment tab function")
if IsWorld or IsDungeon then
    Toggles.AutoSellToggle:OnChanged(function(ChangedValue) -- auto sell
        if ChangedValue then
            local Success, Result = pcall(function()
                local pItems = ProfileInventory:WaitForChild("Items")
                ConnectionTable["ConnectInventory"] = pItems.ChildAdded:Connect(function(NewItem)
                    ItemSellCheck(NewItem)
                end)
            end)
            if not Success then
                SaveErrorToFile("AUTO SELL", Result)
            end
        else
            DisconnectVariable("ConnectInventory")
            SellItemCheck = 0
        end
    end)
end
end -- for unloaded inventory tab

if not SV.GuildTab then -- for unloaded guild tab
SetGlobal("creating guild tab")
local GuildTab = Window:AddTab({
    Name = "Guild",
    Icon = "rbxassetid://9671046895"
})
local GuildTabLeft = GuildTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = GuildTabLeft:AddTab("Main")
    local SecondTab = GuildTabLeft:AddTab("Settings")
local GuildTabRight = GuildTab:AddRightTabbox("Right Tabbox")
    local ThirdTab = GuildTabRight:AddTab("Advanced")
    local FourthTab = GuildTabRight:AddTab("Guild spy")

CreateToggles({
    { "WaitTimeToggle", Text = "Wait for legit time", Tooltip = "Starts the dungeon and then waits a predetermined amount of time before continuing to clear the dungeon", Tab = FirstTab },
    { "DoAllDungeonsToggle", Text = "Do all dungeons", Tooltip = "Starts from whatever dungeon you're currently in and goes to the next dungeon once it's completed. Does not go back for previous dungeons!\n\nOrder dungeons are started in:\ninf -> towers 1-6 -> celestial -> all dungeons", Tab = FirstTab },
    { "DelayInfFloorToggle", Text = "Delay inf tower floors", Tooltip = "When doing infinite tower the script no longer automatically teleports to the next floor and will let the default countdown teleport you to the next floor.", Tab = FirstTab },
    { "GuildQuestToggle", Text = "Auto claim guild quests", Tab = FirstTab }
})

    FirstTab:AddDivider({Margin = -5})
FirstTab:AddDropdown("DoAllDropdown", {
    Values = {
        "Stop",
        "Loop",
        "Loop w/o inf",
        "Loop w/o towers",
        "Play nightmare dungeons"
    },
    Multi = false,
    Text = "Action when finished",
    AllowNull = false,
    Default = "Stop"
})
SecondTab:AddLabel("Add extra wait time", true)
SecondTab:AddSlider("AddExtraTimeSlider", {
    Text = "Seconds",
    Default = 0,
    Min = 0,
    Max = 180,
    Rounding = 0,
    Compact = true,
    Tooltip = "Adds more time to the `Wait for a legit time` option if you don't think the scirpt is waiing long enough, or you want to wait longer for safety.",
    Callback = function(ChangedValue)
        SV.AddedGuildTime = ChangedValue
    end
})
SecondTab:AddLabel("Increment inf tower delay ", true)
SecondTab:AddSlider("IncrementInfiniteSlider", {
    Text = "Seconds",
    Default = 0,
    Min = 0,
    Max = 10,
    Rounding = 0,
    Compact = true,
    Tooltip = "When using `Delay inf tower floors` this toggle will add increasingly more tine to wait after each boss floor has been completed.",
    Callback = function(ChangedValue)
        SV.IncrementInfiniteDelay = ChangedValue
    end
})
SV.TotalGuildPointLabel = ThirdTab:AddLabel("Total Guild Points: ?", false)
ThirdTab:AddInput("TotalKillInput", {
    Text = "Stop after X total points",
    Default = "",
    Placeholder = "number here",
    Callback = function(ChangedValue)
        if IsDungeon then
            SV.StopAfterTotalPoints = ChangedValue
        end
    end
})
    ThirdTab:AddDivider({Margin = -5})
SV.DailyGuildPointLabel = ThirdTab:AddLabel("Daily Guild Points: ?", false)
ThirdTab:AddInput("DailyKillInput", {
    Text = "Stop after X daily points",
    Default = "",
    Placeholder = "number here",
    Callback = function(ChangedValue)
        if IsDungeon then
            SV.StopAfterDailyPoints = ChangedValue
        end
    end
})
local SpyOnGuild = FourthTab:AddLabel("No guild to spy on", true)
    FourthTab:AddDivider()
local StoredPoints
local StoredChatLogs
local StoredDescription
local function ClipboardCheck(Copy, Data)
    if IsMainMenu then
        return true
    end

    if not Options.GuildNamesDropdown.Value then
        SpyOnGuild:SetText("No guild selected")
        return true
    end

    if Copy and Data then
        setclipboard(Data)
        return true
    end
end
local function GetGuildPoints(Copy)
    if ClipboardCheck(Copy, StoredPoints) then
        return
    end

    local GetCache = Remotes:WaitForChild("Guilds_GetCache", math.huge)
    local CachedGuild = GetCache:InvokeServer(string.upper(Options.GuildNamesDropdown.Value))
    local CachedMembers = CachedGuild and CachedGuild.Members
    if not CachedMembers then
        SV.SpyOnGuild:SetText("This guilds data is no longer available")
    end

    local PlayerPoints = {}
    local TotalPoints = 0
    for Index, Data in CachedMembers do
        table.insert(PlayerPoints, string.format(
            "%* - %s",
            Data.UserName, FormatNumber(Data.Points)
        ))
        TotalPoints += tonumber(Data.Points)
    end
    StoredPoints = string.format(
        "Total guild points: %s\n%*",
        FormatNumber(TotalPoints), table.concat(PlayerPoints, "\n")
    )
    if not Copy then
        SpyOnGuild:SetText(StoredPoints)
    else
        setclipboard(StoredPoints)
    end
end
local function GetGuildDescription(Copy)
    if ClipboardCheck(Copy, StoredDescription) then
        return
    end

    local GetCache = Remotes:WaitForChild("Guilds_GetCache", math.huge)
    local CachedGuild = GetCache:InvokeServer(string.upper(Options.GuildNamesDropdown.Value))
    local CachedDescription = CachedGuild and CachedGuild.Description
    if not CachedDescription then
        SpyOnGuild:SetText("This guilds data is no longer available")
    end
    if not Copy then
        SpyOnGuild:SetText(CachedDescription)
        StoredDescription = CachedDescription
    else
        setclipboard(CachedDescription)
    end
end
FourthTab:AddDropdown("GuildNamesDropdown", {
    Values = {},
    Text = "Guilds",
    Multi = false,
    AllowNull = true,
    Default = "",
    MaxVisibleDropdownItems = 5,
    Searchable = true,
    Callback = function()
        StoredPoints = nil
        StoredDescription = nil
        StoredChatLogs = nil
    end
})
FourthTab:AddButton({
    Text = "Scan for guilds",
    Func = function()
        local ScannedGuilds = {}
        local UniqueGuilds = {}
        for Index, Player in Players:GetChildren() do
            local PlayersGuild = GetGuild(Player)
            if PlayersGuild ~= "❌" and not ScannedGuilds[PlayersGuild] then
                ScannedGuilds[PlayersGuild] = true
                table.insert(UniqueGuilds, PlayersGuild)
            end
        end
        Options.GuildNamesDropdown:SetValues(UniqueGuilds)
    end
})
FourthTab:AddButton({
    Text = "Players points",
    Func = function()
        GetGuildPoints()
    end
}):AddButton({
    Text = "Clipboard",
    Func = function()
        GetGuildPoints(true)
    end
})
FourthTab:AddButton({
    Text = "Description",
    Func = function()
        GetGuildDescription()
    end
}):AddButton({
    Text = "Clipboard",
    Func = function()
        GetGuildDescription(true)
    end
})
end -- for unloaded guild tab

if not SV.ShopsTab then -- for unloaded shops tab
SetGlobal("creating shop tab")
local ShopTab = Window:AddTab({
    Name = "Shops",
    Icon = "rbxassetid://12281229733"
})
local LeftTab = ShopTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Egg")
    local SecondTab = LeftTab:AddTab("Nightmare")
    local ThirdTab = LeftTab:AddTab("PVP")
local RightTab = ShopTab:AddRightTabbox("Left Tabbox")
    local FourthTab = RightTab:AddTab("Guild")
    local FifthTab = RightTab:AddTab("Event")

local BuyEggList = {
    { InternalName = "StarEgg", VisualName = "Star egg", CoinPrice = 2000, CurrencyType = "Gold" },
    { InternalName = "JungleEgg", VisualName = "Jungle egg", CoinPrice = 5000, CurrencyType = "Gold" },
    { InternalName = "CrystalEgg", VisualName = "Crystal egg", CoinPrice = 7500, CurrencyType = "Gold" },
    { InternalName = "DesertEgg", VisualName = "Pharaoh's egg", CoinPrice = 10000, CurrencyType = "Gold" },
    { InternalName = "ChristmasEgg", VisualName = "Holiday egg", CoinPrice = 400, CurrencyType = "Crystal" }
}
FirstTab:AddDropdown("EggShopDropdown", {
    Values = {},
    Multi = false,
    Text = "egg name (price)",
    AllowNull = true,
    Default = nil,
    Searchable = true,
    Callback = function(ChangedValue)
        if ChangedValue and IsWorld or IsDungeon then
            SV.SelectedEggItem = BuyEggList[ChangedValue]
        else
            SV.SelectedEggItem = nil
        end
    end
})
BuyEggList = BuildShopValues("EggShopDropdown", BuyEggList)
FirstTab:AddButton({
    Text = "Buy egg",
    Func = function()
        local TableReference = SV.SelectedEggItem
        if not TableReference then
            Library:Notify("No egg is selected", 3)
            return
        end
        if not BuyFromEggShop(TableReference.CurrencyType, TableReference.InternalName, TableReference.CoinPrice, TableReference.VisualName) then
            Library:Notify("You do not have enough gold", 3)
        end
    end
})
CreateToggles({
    { "AutoHatchEggToggle", Text = "Auto hatch selected egg", Tooltip = "Recommended to do this in dungeons where no one else can see you (lag is also reduced)", Tab = FirstTab },
    { "AutoHatchInventoryEggToggle", Text = "Hatch eggs in inventory", Tooltip = "Hatch eggs in inventory", Tab = FirstTab}
})
FirstTab:AddSlider("EggHatchDelaySlider", {
    Text = "Egg hatch delay",
    Default = 0,
    Min = 0,
    Max = 10,
    Rounding = 0,
    Callback = function(ChangedValue)
        if IsWorld or IsDungeon then
            SV.HatchDelay = ChangedValue
        end
    end
})
for Dropdown, Info in ipairs{
    { "NightmareShopDropdown", ShopList = "NightmarePortals", Currency = "Nightmare", RequiredWorld = "14914684761", ReqName = "world 10", ToggleName = "AutoNightmareToggle", Tab = SecondTab },
    { "PVPShopDropdown", ShopList = "PVPShop", Currency = "PvP", RequiredWorld = "6510868181", ReqName = "pvp arena", ToggleName = "AutoPvpToggle", Tab = ThirdTab },
    { "GuildShopDropdown", ShopList = "GuildShop", Currency = "Guild", RequiredWorld = "139316833473171", ReqName = "guild hub", ToggleName = "AutoGuildToggle", Tab = FourthTab },
    { "EventShopDropdown", ShopList = "Halloween2026", Currency = "Halloween", RequiredWorld = "5862275930", ReqName = "event hub", ToggleName = "AutoEventToggle", Tab = FifthTab }
} do
    local SelectedItem
    Info.Tab:AddDropdown(tostring(Info[1]), {
        Values = {},
        Multi = false,
        Text = "item name ("..Info.Currency.." coins)",
        AllowNull = true,
        Default = nil,
        MaxVisibleDropdownItems = 5,
        Searchable = true,
        Callback = function(ChangedValue)
            if ChangedValue and IsWorld then
                SelectedItem = Info.ShopList[ChangedValue]
            else
                SelectedItem = nil
            end
        end
    })
    Info.ShopList = BuildShopValues(tostring(Info[1]), Info.ShopList)
    Info.Tab:AddButton({
        Text = "Buy item",
        Func = function()
            if Info.RequiredWorld then
                if StringPlaceID ~= Info.RequiredWorld then
                    Library:Notify(string.format(
                        "Go to %* to do this",
                        Info.ReqName
                    ), 5)
                    return
                end
            end
            BuyFromLocalShop(Info.ShopList, SelectedItem)
        end
    })
    local AutoBuy
    Info.Tab:AddToggle(Info.ToggleName, {
        Text = "Buy max selected item",
        Default = false,
        Callback = function(ChangedValue)
            if ChangedValue and (IsWorld or IsDungeon) and StringPlaceID == Info.RequiredWorld then
                AutoBuy = true
                local Success, Result = pcall(function()
                    repeat
                        BuyFromLocalShop(Info.ShopList, SelectedItem)
                        task.wait()
                    until not AutoBuy
                end)
                if not Success then
                    SaveErrorToFile(Info.Currency, Result)
                end
            else
                AutoBuy = nil
            end
        end
    })
end
end -- for unloaded shops tab

if not SV.QuickMenusTab then -- for unloaded quick menus tab
SetGlobal("creating quick menu tab")
local OpenMenuTab = Window:AddTab({
    Name = "Quick menus",
    Icon = "rbxassetid://13534579488"
})
local LeftTab = OpenMenuTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Main")
local RightTab = OpenMenuTab:AddRightTabbox("Left Tabbox")
    local SecondTab = RightTab:AddTab("Extra")

CreateToggles({
    { Button = true, Text = "Teleport menu (old)", Tab = FirstTab, AttachedFunction = OpenMenu, FunctionValue = "HubTeleport" },
    { Button = true, Text = "Bank", Tab = FirstTab, AttachedFunction = OpenMenu, FunctionValue = "Bank" },
    { Button = true, Text = "Upgrade station", Tab = FirstTab, AttachedFunction = OpenMenu, FunctionValue = "ItemUpgrade" },
    { Button = true, Text = "Sell station", Tab = FirstTab, AttachedFunction = OpenMenu, FunctionValue = "Sell" },
    { Button = true, Text = "Zero altar", Tab = FirstTab, AttachedFunction = OpenMenu, FunctionValue = "Fusion" },
    { Button = true, Text = "Pet fusion", Tab = FirstTab, AttachedFunction = OpenMenu, FunctionValue = "FusePets" },
    { Button = true, Text = "Salon", Tab = SecondTab, AttachedFunction = OpenMenu, FunctionValue = "NewCharacterCustomizer" },
    { Button = true, Text = "Recycler", Tab = SecondTab, AttachedFunction = OpenMenu, FunctionValue = "Recycler" },
    { Button = true, Text = "Furniture shop", Tab = SecondTab, AttachedFunction = OpenMenu, FunctionValue = "FurnitureShop" },
    { Button = true, Text = "Pet adventures", Tab = SecondTab, AttachedFunction = OpenMenu, FunctionValue = "PetExpeditions" },
})
end -- for unloaded quick menus tab

if not SV.MiscellaneousTab then -- for unloaded miscellaneous
local MiscTab = Window:AddTab({
    Name = "Miscellaneous",
    Icon = "rbxassetid://4801326994"
})
local LeftTab = MiscTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Main")
    local SecondTab = LeftTab:AddTab("Hide ui's")
local RightTab = MiscTab:AddRightTabbox("Right Tabbox")
    local ThirdTab = RightTab:AddTab("Extra")
    local FourthTab = RightTab:AddTab("Performance")

local function ToggleMenu(ChangedValue, FirstMenu)
    local Success, Result = pcall(function()
        local FoundMenu = PlayerGui:FindFirstChild(FirstMenu)
        if FoundMenu and ChangedValue then
            FoundMenu.Enabled = false
        elseif FoundMenu and not ChangedValue then
            FoundMenu.Enabled = true
        end
    end)
    if not Success then
        SaveErrorToFile("MENU TOGGLE", Result)
    end
end
ThirdTab:AddInput("JoinPlayerInput", {
    Text = "Enter name",
    Default = "",
    Placeholder = "username",
    Tooltip = "Enter a players exact actual name (not display) and teleport to them if they are currently in game and not in a dungeon.",
})
ThirdTab:AddButton({
    Text = "Join player",
    Tooltip = "Attempts to join the players name entered into the field above",
    Func = function()
        if not Options.JoinPlayerInput.Value or IsMainMenu or Options.JoinPlayerInput.Value == "" then
            return
        end
        if SV.CanRequire then
            local rTeleport = require(Teleport)
            rTeleport:TeleportToPlayer(LocalPlayer, Players:GetUserIdFromNameAsync(Options.JoinPlayerInput.Value), nil, true)
            Library:Notify("Attempting to join player: " ..Options.JoinPlayerInput.Value, 5)
        else
            Library:Notify("Your executor doesn't support this", 5)
        end
    end
})
    ThirdTab:AddDivider({Margin = -5})
CreateToggles({
    { "MobCameraToggle", Text = "Camera on mob", Tooltip = "Positions the players camera on the current target mob", Tab = FirstTab },
    { "DamageNumbersToggle", Text = "Remove damage numbers", Tooltip = "Prevents damage numbers from being rendered", Tab = FirstTab },
    { "DamageFlashToggle", Text = "Hide damage flash", Tooltip = "Hides the red flash when mobs are damaged", Tab = FirstTab },
    { "DeathEffectToggle", Text = "Remove death effects", Tooltip = "Prevents all death effects from being rendered", Tab = FirstTab },
    { "KnockdownToggle", Text = "Disable knockdown", Tooltip = "Prevents the knockdown status from working (everyone can see this if they look at your statuses)", Tab = FirstTab },
    { "ShowEndTimeToggle", Text = "Display end time", Tooltip = "Show the dungeons clear time when finished", Tab = FirstTab },
    { "WaystoneToggle", Text = "Closest waystone", Tooltip = "Hide the icon for the closest waystone", Tab = SecondTab },
    { "MissionObjectiveToggle", Text = "Mission objective", Tooltip = "Hide the text on your screen telling you what to do", Tab = SecondTab, AttachedFunction = ToggleMenu, FunctionValue = "MissionObjective" },
    { "BossBarToggle", Text = "Boss bar", Tooltip = "Hide boss bars on your screen", Tab = SecondTab, AttachedFunction = ToggleMenu, FunctionValue = "BossHealthbar" },
    { "PlayerHotbarToggle", Text = "Hotbar", Tooltip = "Hide your health and skill ui", Tab = SecondTab, AttachedFunction = ToggleMenu, FunctionValue = "Hotbar" },
    { "MobilePlayerSkills", Text = "Mobile skills", Tooltip = "Hide the mobile skill ui", Tab = SecondTab, AttachedFunction = ToggleMenu, FunctionValue = "TouchInput" },
    { "MainGuiToggle", Text = "Event icon", Tooltip = "Hide the event icon", Tab = SecondTab, AttachedFunction = ToggleMenu, FunctionValue = "MainGui" },
    { "HideMenuToggle", Text = "Menu", Tooltip = "Hide the in-game gui tab", Tab = SecondTab, AttachedFunction = ToggleMenu, FunctionValue = "Menu" },
    { "DevKickToggle", Text = "Kick on dev join", Tooltip = "Kick you from the game if a dev joins you", Tab = ThirdTab },
    { "ProfilerToggle", Text = "Show account info", Tooltip = "Display basic information about the account being used", Tab = ThirdTab },
    { "AFKToggle", Text = "Anti AFK", Tooltip = "Prevents you from being AFk kicked (may not work on all executors)", Tab = ThirdTab },
    { "MainMenuPlay", Text = "Auto click play", Tooltip = "Automatically clicks \"PLAY\" when on the main menu", Tab = ThirdTab },
    { "AutoJoinDungeon", Text = "Auto join dungeon", Tooltip = "Automatically join a nightmare dungeon if available", Tab = ThirdTab },
    { "MobESPToggle", Text = "Mob ESP", Tooltip = "Adds a highlight to mobs", Tab = ThirdTab },
    { "NoclipCameraToggle", Text = "Noclip camera", Tooltip = "Allows your camera to clip through walls", Tab = ThirdTab },
    { "DisableAutoJumpToggle", Text = "Disable autojump", Tooltip = "Prevents you from auto-jumping on mobile devices", Tab = ThirdTab },
    { "RemoveOtherPlayersToggle", Text = "Remove other players", Tooltip = "Removes all other players including their pets", Tab = FourthTab },
    { "DisableRenderingToggle", Text = "Disable rendering", Tooltip = "Sigificantly reduces the load on your GPU by disabling 3d rendering", Tab = FourthTab },
    { "PreventEffectsToggle", Text = "Don't render new effects", Tooltip = "Stops the game from rendering new effects such as projectiles!\nDO NOT USE IF PLAYING NORMALLY", Tab = FourthTab },
    { "PreventMobToggle", Text = "Don't render new models", Tooltip = "Stops the game from rendering most new models your game hasn't already rendered", Tab = FourthTab }
})
    FirstTab:AddDivider({Margin = -5})
local rWalkspeedManager
FirstTab:AddSlider("WalkspeedSlider", {
    Text = "Change walkspeed",
    Default = 28,
    Min = 28,
    Max = 200,
    Rounding = 0,
    Tooltip = "Does exactly what you think it does",
    Callback = function(ChangedValue)
        if SV.CanRequire then
            if not rWalkspeedManager then
                rWalkspeedManager = require(rWalkspeedManager)
            end
            rWalkspeedManager:SetBaseSpeed(tonumber(ChangedValue))
        end
    end
})
    ThirdTab:AddDivider({Margin = -5})
ThirdTab:AddInput("ChangeClassColor", {
    Text = "Change class colors",
    Default = "",
    Placeholder = "FFFFFF",
    Tooltip = "Changes the colors of your classes attacks on your client only",
    Callback = function(ChangedValue)
        if IsDungeon or IsWorld then
            LocalPlayer:SetAttribute("ClassColor", ChangedValue)
        end
    end
})
    FourthTab:AddDivider({Margin = -5})
FourthTab:AddSlider("FPSSlider", {
    Text = "Change FPS",
    Default = 60,
    Min = 20,
    Max = 240,
    Rounding = 0,
    Callback = function(ChangedValue)
        if setfpscap then
            setfpscap(tonumber(ChangedValue))
        end
    end
})
end -- for unloaded miscellaneous

if not SV.DiscordTab then -- for unloaded discord tab
local DiscTab = Window:AddTab({
    Name = "Discord",
    Icon = "rbxasset://textures/ui/LuaApp/ExternalSite/discord@3x.png"
})
local LeftTab = DiscTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Main")
    local SecondTab = LeftTab:AddTab("Settings")
local RightTab = DiscTab:AddRightTabbox("Right Tabbox")
    local ThirdTab = RightTab:AddTab("Join the discord")

FirstTab:AddInput("WebhookLinkInput", {
    Text = "Webhook link",
    Default = "",
    Placeholder = "https://discord.com/api/webhooks/",
    Callback = function(ChangedValue)
        if string.find(ChangedValue, "https://discord.com/api/webhooks/") then
            SV.DiscordWebhookLink = ChangedValue
        else
            SV.DiscordWebhookLink = nil
        end
    end
})

local function ToggleValue(ChangedValue, ToggleValue)
    if ChangedValue and not IsMainMenu then
        SV[tostring(ToggleValue)] = true
    else
        SV[tostring(ToggleValue)] = nil
    end
end

CreateToggles({
    { "DungeonLoggerToggle", Text = "Log dungeons", Tooltip = "Send a message to the webhook provided going over the details of the dungeon after it's finished", Tab = FirstTab, AttachedFunction = ToggleValue, FunctionValue = "DungeonPing" },
    { "PerkPingToggle", Text = "Ping for perk drops", Tooltip = "Sends a ping to the webhook provided if you've received an item with a perk you are wanting to keep", Tab = FirstTab, AttachedFunction = ToggleValue, FunctionValue = "PerkPing" },
    { "ClassPingToggle", Text = "Ping for class mastery", Tooltip = "Sends a ping to the webhook provided once you've unlocked the Mastery Class for the class you're currently using if one is available", Tab = FirstTab },
    { "NightmarePingToggle", Text = "Ping for nightmare cap", Tooltip = "Sends a ping to the webhook provided once you've reached your limits on Nightmare Dungeon clears", Tab = FirstTab, AttachedFunction = ToggleValue, FunctionValue = "NightmarePing" },
    { "GuildPingToggle", Text = "Ping for guild cap", Tooltip = "Sends a ping to the webhook provided once you've reached your point limits on Guild Points", Tab = FirstTab, AttachedFunction = ToggleValue, FunctionValue = "GuildPing" },
    { "EventBossPingToggle", Text = "Ping for event boss cap", Tooltip = "Sends a ping to the webhook provided once you've reached your limits on event boss clears", Tab = FirstTab, AttachedFunction = ToggleValue, FunctionValue = "EventPing" },
    { "ShowPlayersToggle", Text = "Party member details", Tooltip = "Shows everyone inside of the party instead of only showing the number of players in the party", Tab = SecondTab }
})
SecondTab:AddDropdown("PingDropdown", {
    Values = {
        [""] = "none",
        ["@here"] = "@here",
        ["@everyone"] = "@everyone"
    },
    Multi = false,
    Text = "Ping options",
    AllowNull = false,
    Default = "@everyone",
    Callback = function(ChangedValue)
        DiscordPingType = tostring(ChangedValue)
    end
})
SecondTab:AddButton({
    Text = "Send test message",
    Tooltip = "Useful for checking if your webhook provided is working properly",
    DoubleClick = true,
    Func = function()
        if not request then
            Library:Notify("Your executor doesn't allow requests", 5)
        end
        pcall(function()
            local MessageContent = {
                ["username"] = "test",
                ["content"] = "test " ..DiscordPingType
            }
            RequestMessage(SV.DiscordWebhookLink, MessageContent, false)
        end)
    end
})
ThirdTab:AddLabel("if you wish to get news about <font color='#33FF33'>updates</font> and <font color='#33FF33'>changes</font> to the script, or <font color='#ff3333'>report issues</font>, then consider joining the <font color='#5650F6'>discord</font>!", true)
ThirdTab:AddButton({
    Text = "Copy discord invite link",
    Tooltip = "The invite will be copied to your devices clipboard!",
    Func = function()
        local Success, Result = pcall(function()
            setclipboard("https://discord.gg/bNWWpqFZbP")
        end)
        if not Success then
            Library:Notify("Your executor doesn't allow this", 5)
        end
    end
})
end -- for unloaded discord tab

if not SV.ConfigurationTab then -- for unloaded config tab
SetGlobal("creating config tab")
ConfigTab = Window:AddTab({
    Name = "Configurations",
    Icon = "rbxassetid://9671045892"
})
local LeftTab = ConfigTab:AddLeftTabbox("Left Tabbox")
    local FirstTab = LeftTab:AddTab("Main")
    local SecondTab = LeftTab:AddTab("debug")

CreateToggles({
    { "HideGuiToggle", Text = "Hide menu when executed", Tab = FirstTab },
    { "AutoScriptToggle", Text = "Auto execute script", Tab = FirstTab }
})

    FirstTab:AddDivider({Margin = -5})
local LastUpdated
FirstTab:AddDropdown("UnloadTabDropdown", {
    Values = {
        ["GeneralTab"] = "General",
        ["EventTab"] = "Events",
        ["TradingTab"] = "Trading",
        ["ClassesTab"] = "Classes",
        ["InventoryTab"] = "Inventory",
        ["DungeonsTab"] = "Dungeons",
        ["GuildTab"] = "Guild",
        ["ShopsTab"] = "Shops",
        ["QuickMenusTab"] = "Quick menus",
        ["MiscellaneousTab"] = "Miscellaneous",
        ["DiscordTab"] = "Discord"
    },
    Multi = true,
    AllowNull = true,
    Default = "",
    MaxVisibleDropdownItems = 5,
    Searchable = true,
    Tooltip = "Any selected tab and its respective functions will not be loaded the next time the script is run. Unselecting a tab will allow it and its functions to load when the script is next ran.\n<font color='#ff3333'>IF YOU SELECT A TAB <u>NOTHING</u> FROM IT WILL BE LOADED AND IF YOU HAVE ANYTHING FROM THOSE TABS SAVED THEN ANY CHANGES TO THE CONFIG AFTER THEY ARE UNLOADED WILL NOT BE SAVED</font>",
    Text = "Don't load tabs",
    Callback = function(ChangedValue)
        if ChangedValue then
            local LastChanged = time()+2
            LastUpdated = LastChanged
            if LastChanged == LastUpdated then
                local TabsToUnload = {}
                for Tab in ChangedValue do
                    table.insert(TabsToUnload, tostring(Tab))
                end
                writefile("JDRS/SkipTabs", HttpService:JSONEncode(TabsToUnload))
            end
            LastUpdated = nil
        end
    end
})
    FirstTab:AddDivider({Margin = -5})
FirstTab:AddButton({
    Text = "Stop script from executing",
    Func = function()
        local FileName = "JDRS/AutoExecute"
        if isfile(FileName) then
            delfile(FileName)
        end
        if EF.ClearQueue then
            Library:Notify("Script will not be ran when you teleport. Hopefully you enjoyed using it without encountering any issues!\n -JDRS", 10)
            EF.ClearQueue()
        end
    end
})
FirstTab:AddButton({
    Text = "<font color='#ff3333'>Kill the script</font>",
    Tooltip = "unloads the script and garbage collects it, if you see errors in the console after doing this you can ignore them.",
    DoubleClick = true,
    Func = function()
        KillSwitch = true
        CleanUpScript(true)
        print("JDRS: script has been unloaded")
    end
})
        SecondTab:AddLabel("These options should only be used when attempting to report issues with the script, they are intentionally vague as I know what they are referring to.", true)
        SecondTab:AddDivider({Margin = -5})
        SecondTab:AddToggle("MobDebugToggle", {
            Text = "print debugs",
            Tooltip = "prints what the script does when a mob is created",
            Default = false,
            Callback = function(ChangedValue)
                if ChangedValue and (IsDungeon or IsWorld) then
                    ISV.Debug = true
                    Library:Notify("Tracked debugs will now be printed to the f9 console")
                else
                    ISV.Debug = nil
                end
            end
        })
        SecondTab:AddButton({
            Text = "print current mob",
            Tooltip = "prints the mob that the script is currently trying to target",
            Func = function()
                if not IsDungeon then
                    warn("No mobs are being targeted, not in dungeon.")
                    return
                end
                local TargetMob = CurrentMob
                if not TargetMob then
                    print("JDRS: no mob is a target")
                    return
                end
                local TargetMobReference = ISV.MobTable[TargetMob]
                local MobString = "JDRS: current target is " .. TargetMob.Name
                if TargetMobReference then
                    if TargetMobReference.Invincible then
                        MobString = MobString .. " (invincible)"
                    end
                    if TargetMobReference.IsBlocker then
                        MobString = MobString .. " (blocker, highest priority)"
                    end
                    if TargetMobReference.Priority then
                        MobString = MobString .. " (priority)"
                    end
                    if TargetMobReference.NoData then
                        MobString = MobString .. " (no data)"
                    end
                    MobString = MobString .. " Path: " ..tostring(TargetMob:GetFullName())
                end
                print(MobString)
                Library:Notify("Printed current target to console")
            end
        })
        SecondTab:AddButton({
            Text = "print target mobs",
            Tooltip = "prints the mobs the script is targeting",
            Func = function()
                if not IsDungeon then
                    warn("No mobs are being targeted, not in dungeon.")
                    return
                end
                local MobString = "JDRS current mobs: " ..tostring(IsAliveMobs).. "\n"
                for Mob, Info in ISV.MobTable do
                    MobString = MobString .. tostring(Mob)
                    if Info.Invincible then
                        MobString = MobString .. " (invincible)"
                    end
                    if Info.IsBlocker then
                        MobString = MobString .. " (blocker, highest priority)"
                    end
                    if Info.Priority then
                        MobString = MobString .. " (priority)"
                    end
                    if Info.NoData then
                        MobString = MobString .. " (no data)"
                    end
                    MobString = MobString .. " Path: " .. tostring(Mob:GetFullName())
                    if Mob == CurrentMob then
                        MobString = MobString .. " (current target)"
                    end
                    MobString = MobString .."\n"
                end
                print(MobString)
                Library:Notify("Printed targets to console")
            end
        })
        SecondTab:AddButton({
            Text = "print target objects",
            Tooltip = "prints the objects the script is trying to teleport",
            Func = function()
                if not IsDungeon then
                    warn("No objects are being teleported, not in dungeon.")
                    return
                end
                local ObjString = "JDRS current objects:\n"
                for Part, Info in TeleportParts do
                    ObjString = ObjString .. string.format(
                        "%* %*Path: %*\n",
                        Part, Info and Info.Regenerates and "(regenerates) " or "", Part:GetFullName()
                    ) 
                end
                print(ObjString)
                Library:Notify("Printed objects to console")
            end
        })
        SecondTab:AddButton({
            Text = "open console",
            Tooltip = "Opens the roblox console if you can't use the chat or don't want to.",
            Func = function()
                StarterGui:SetCore("DevConsoleVisible", true)
            end
        })
        SecondTab:AddButton({
            Text = "remote spy",
            Tooltip = "Loads a script used to view remote events/remote functions.\n(if closed you might crash)\n\n<font color='#FCCE7E'>Script credits:</font> upio and deivid",
            Func = function()
                Library:Notify("Cobalt is being loaded")
                loadstring(game:HttpGet("https://gitlab.com/upio/cobalt/-/releases/permalink/latest/downloads/Cobalt.luau"))()
            end
        })
        SecondTab:AddButton({
            Text = "dex",
            Tooltip = "Loads a script used to view the games workspace.\n\n<font color='#FCCE7E'>Script credits:</font> chillz",
            Func = function()
                Library:Notify("Dex is being loaded")
                loadstring(game:HttpGet("https://github.com/AZYsGithub/DexPlusPlus/releases/latest/download/out.lua"))()
            end
        })
        SecondTab:AddButton({
            Text = "force restart dungeon",
            DoubleClick = true,
            Func = function()
                if IsDungeon then
                    ReplayDungeonLoop(ISV.MissionId, ISV.LoggedDifficulty)
                end
            end
        })
        CompatibilityButton = SecondTab:AddButton({
            Text = "check compatibility",
            Tooltip = "Creates a bunch of text labels in place of this button showing compatibility of important functions used by the script",
            Func = function()
                    SecondTab:AddDivider({Margin = -5})
                local RequireLabel = SecondTab:AddLabel("require: ?", true)
                local HookfunctionLabel = SecondTab:AddLabel("hookfunction: ?", true)
                local RestorefunctionLabel = SecondTab:AddLabel("restorefunction: ?", true)
                local UpvalueLabel = SecondTab:AddLabel("getupvalue: ?", true)
                local NewcclosureLabel = SecondTab:AddLabel("newcclosure: ?", true)
                local AutoInjectLabel = SecondTab:AddLabel("queueonteleport: ?", false)
                local RequestLabel = SecondTab:AddLabel("request: ?", true)
                local InvisTeleportLabel = SecondTab:AddLabel("invisible teleport: ?", true)
                if SV.CanRequire then
                    RequireLabel:SetText("require: <font color='#33ff33'>Yes</font>")
                else
                    RequireLabel:SetText("require: <font color='#ff3333'>No</font>")
                end

                if EF.Hook then
                    HookfunctionLabel:SetText("hookfunction: <font color='#33ff33'>Yes</font>")
                else
                    HookfunctionLabel:SetText("hookfunction: <font color='#ff3333'>No</font>")
                end

                if EF.ClearHook then
                    RestorefunctionLabel:SetText("restorefunction: <font color='#33ff33'>Yes</font>")
                else
                    RestorefunctionLabel:SetText("restorefunction: <font color='#ff3333'>No</font>")
                end

                if debug and debug.getupvalue then
                    UpvalueLabel:SetText("getupvalue: <font color='#33ff33'>Yes</font>")
                else
                    UpvalueLabel:SetText("getupvalue: <font color='#ff3333'>No</font>")
                end

                if EF.NewClosure then
                    NewcclosureLabel:SetText("newcclosure: <font color='#33ff33'>Yes</font>")
                else
                    NewcclosureLabel:SetText("newcclosure: <font color='#ff3333'>No</font>")
                end

                if EF.Queue then
                    AutoInjectLabel:SetText("queueonteleport: <font color='#33ff33'>Yes</font>")
                else
                    AutoInjectLabel:SetText("queueonteleport: <font color='#ff3333'>No</font>")
                end

                if EF.SendRequest then
                    RequestLabel:SetText("request: <font color='#33ff33'>Yes</font>")
                else
                    RequestLabel:SetText("request: <font color='#ff3333'>No</font>")
                end

                if EF.Desync and EF.RaknetFunction.is_enabled() then
                    InvisTeleportLabel:SetText("Can invisibly teleport: <font color='#33ff33'>Yes</font>", false)
                else
                    InvisTeleportLabel:SetText("invisible teleport: <font color='#ff3333'>No</font>")
                end
                CompatibilityButton:Destroy()
                CompatibilityButton = nil
            end
        })
end -- for unloaded config tab
SetGlobal("creating UI functions")

if not SV.GeneralTab then
SetGlobal("general tab functions")
if IsDungeon then
    local KillauraChanged
    Toggles.KillauraToggle:OnChanged(function(ChangedValue) -- killaura
        local TimeActivated = os.clock()
        KillauraChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= KillauraChanged then
            return
        end
        
        if ChangedValue then
            if not Class then
                Library:Notify("CLASS NOT YET SUPPORTED", 9999999999999999)
                return
            end
            SV.Killaura = true
            local Success, Result = pcall(function()
                ConnectionTable["ConnectClass"] = LocalPlayer:GetAttributeChangedSignal("Class"):Connect(function()
                    Class = GetPlayerClass()
                end)
                if SV.CanRequire then
                    pcall(function()
                        local Actions = require(Client:WaitForChild("Actions", math.huge))
                        Actions:SetSkillDisabled("Primary", true)
                        Actions:SetSkillDisabled("Skill1", true)
                        Actions:SetSkillDisabled("Skill2", true)
                        Actions:SetSkillDisabled("Skill3", true)
                        Actions:SetSkillDisabled("Ultimate", true)
                    end)
                end
                local LowerAttack = Vector3.new(0, 3, 0)
                local CAttack = Remotes:WaitForChild("Combat_Attack", math.huge)
                local AttackArgs = {
                    Ranged = function(Skill, AttackPosition)
                        if SV.IsRanged then
                            AttackPosition = AttackPosition - LowerAttack
                        end
                        CAttack:FireServer(Skill, AttackPosition, nil, AntiCheatNumber)
                    end,
                    Melee = function(Skill, AttackPosition)
                        CAttack:FireServer(Skill, PlayerRoot.Position, (AttackPosition - PlayerRoot.Position).Unit, AntiCheatNumber)
                    end,
                    ShadowChain = function(Skill)
                        Skill:FireServer{CurrentMob, CurrentMob, CurrentMob, CurrentMob, CurrentMob}
                    end,
                    TableRemote = function(Skill)
                        Skill:FireServer(CurrentMob)
                    end,
                    Remote = function(Skill)
                        Skill:FireServer()
                    end,
                    GuardianRemote = function(Skill)
                        Skill:FireServer(1, PlayerRoot.Position)
                    end,
                    HunterRemote = function(Skill)
                        Skill:FireServer(PlayerRoot.Position, 50)
                    end,
                    HunterTrapRemote = function(Skill, AttackPosition)
                        Skill:FireServer("BearTrap", AttackPosition)
                    end,
                    PlayerPositionRemote = function(Skill)
                        Skill:FireServer(PlayerRoot.Position)
                    end,
                    MobPositionRemote = function(Skill, AttackPosition)
                        Skill:FireServer(AttackPosition)
                    end,
                    CFrameRemote = function(Skill)
                        Skill:FireServer(PlayerRoot.CFrame)
                    end,
                    PlayerRemote = function(Skill)
                        Skill:FireServer(LocalPlayer)
                    end,
                    StarbreakerWaves = function(Skill, AttackPosition)
                        task.spawn(function()
                            if IsBoss then
                                local Status = PlayerCharacter:FindFirstChild("Status")
                                if Status and Status:FindFirstChild("Starforge") then
                                    for Swing = 1, 5 do
                                        for Hit = 1, 10 do
                                            CAttack:FireServer("StarbreakerWaveSwing" ..tostring(Swing).. "Hit" ..tostring(Hit), PlayerRoot.Position, (AttackPosition - PlayerRoot.Position).Unit, AntiCheatNumber)
                                        end
                                    end
                                end
                            end
                        end)
                    end
                }
                repeat
                    for _, Attack in Class.Skills do
                        if CurrentMob then
                            local AttackCooldown = Attack.Cooldown
                            if time() - (Attack.LastUsed or 0) >= AttackCooldown+AddedDelay+PlayerPing then
                                local AttackType = Attack.Type
                                local MobCollider = CurrentMob:FindFirstChild("Collider")
                                if MobCollider then
                                    local AttackDistance = Attack.Distance
                                    local PlayerSurface = PlayerRoot:GetClosestPointOnSurface(MobCollider.Position)
                                    local MobSurface = MobCollider:GetClosestPointOnSurface(PlayerRoot.Position)
                                    local Distance = (PlayerSurface - MobSurface).Magnitude
                                    if Distance <= AttackDistance then
                                        if SV.Autofarm and IsBoss then
                                            local TpTime = CurrentMob:GetAttribute("T")
                                            if not (TpTime and TpTime+0.2 < time()) then
                                                break
                                            end
                                        end
                                        local FindAttackType = AttackArgs[AttackType]
                                        if FindAttackType then
                                            FindAttackType(Attack.Skill, MobSurface)
                                        else
                                            SV.Killaura = nil
                                            SaveErrorToFile("KILLAURA ATTACK TYPE", "invalid attack type or attack type not supported", AttackType)
                                            break
                                        end
                                        Attack.LastUsed = time()
                                        if DelayAttacks and not IsBoss then
                                            task.wait(DelayAttacks)
                                        end
                                    end
                                end
                            end
                        end
                    end
                    task.wait()
                until not SV.Killaura
            end)
            if not Success then
                SaveErrorToFile("KILLAURA", Result, SV.PlayerClass)
            end
        else
            if SV.CanRequire then
                pcall(function()
                    local Actions = require(Client:WaitForChild("Actions", math.huge))
                    Actions:SetSkillDisabled("Primary", false)
                    Actions:SetSkillDisabled("Skill1", false)
                    Actions:SetSkillDisabled("Skill2", false)
                    Actions:SetSkillDisabled("Skill3", false)
                    Actions:SetSkillDisabled("Ultimate", false)
                end)
            end
            DisconnectVariable("ConnectClass")
            SV.Killaura = nil
        end
    end)
    Toggles.SafeKillauraToggle:OnChanged(function(ChangedValue) -- killaura
        if SV.CanRequire and EF.Hook and EF.ClearHook and EF.NewClosure and EF.CheckHook then
            local Success, Result = pcall(function()
                local Actions = require(Client.Actions)
                if ChangedValue then
                    SV.SafeKillaura = true
                    if SV.IsRanged then
                        Library:Notify("adjust class distances in the \"Classes\" tab if you are too far from the mobs to do damage.", 10)
                    end
                    CreateHookOnFunction(Actions.IsBusy, true)

                    local SkillNames = {
                        "Primary", "Skill1", "Skill2", "Skill3", "Ultimate"
                    }
                    local AttackCount = 1
                    for Index, Skill in SkillNames do
                        if AttackCount == 1 then
                            task.spawn(function()
                                repeat
                                    if CurrentMob then
                                        Actions:UseSkill(Skill)
                                    end
                                    task.wait()
                                until not (SV.SafeKillaura or KillSwitch)
                            end)
                        else
                            task.spawn(function()
                                repeat
                                    if CurrentMob then
                                        Actions:UseSkill(Skill)
                                    end
                                    task.wait(.2)
                                until not (SV.SafeKillaura or KillSwitch)
                            end)
                        end
                        AttackCount = AttackCount + 1
                    end
                    while SV.SafeKillaura do
                        if Actions:IsSheathed() then
                            Actions:UseSkill("Sheath")
                        end
                        task.wait(1)
                    end
                else
                    SV.SafeKillaura = nil
                    CreateHookOnFunction(Actions.IsBusy, false)
                end
            end)
            if not Success then
                SaveErrorToFile("SAFE KILLAURA", Result)
            end
        elseif mouse1click and keyclick then
            local Success, Result = pcall(function()
                if ChangedValue then
                    while SV.SafeKillaura do
                        mouse1click(1, 1)
                        keyclick(Enum.KeyCode.E)
                        keyclick(Enum.KeyCode.R)
                        keyclick(Enum.KeyCode.F)
                        keyclick(Enum.KeyCode.X)
                        task.wait()
                    end
                else
                    SV.SafeKillaura = nil
                end
            end)
            if not Success then
                SaveErrorToFile("SAFE KILLAURA FALLBACK", Result)
            end
        else
            Library:Notify("Your executor doesn't support this", 5)
        end
    end)
    local CurrentCamera = Workspace.CurrentCamera
    local AutofarmChanged
    Toggles.AutoProgressToggle:OnChanged(function(ChangedValue)
        local TimeActivated = os.clock()
        AutofarmChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= AutofarmChanged then
            return
        end

        if ChangedValue then
            SV.Autofarm = true
            task.spawn(function()
                local Success, Result = pcall(function()
                    local RotationAroundMob = 0
                    PlayerRoot.CanCollide = false
                    local LastCollider
                    local TeleportTween
                    while SV.Autofarm do
                        if KillSwitch then
                            break
                        end
                        if TempStop or HoldForRealTime or EventOverride then
                            if TeleportTween then
                                TeleportTween:Cancel()
                                TeleportTween = nil
                            end
                            task.wait(.1)
                            continue
                        end
                        if TeleportMob then
                            PlayerRoot.Velocity = Vector3.zero
                            local MobCollider = TeleportMob and TeleportMob:FindFirstChild("Collider")

                            if MobCollider then
                                local DistanceFromMob = (PlayerRoot.Position - MobCollider.Position).Magnitude
                                local PlayerOffset = Xdistance + (MobCollider.Size.X / 2)
                                RotationAroundMob += MobRotationSpeed / PlayerOffset

                                local TargetCFrame = CFrame.new(MobCollider.Position) * CFrame.Angles(0, math.rad(RotationAroundMob), 0) * CFrame.new(PlayerOffset, Ydistance, 0)
                                TargetCFrame = CFrame.lookAt(TargetCFrame.Position, Vector3.new(MobCollider.Position.X, TargetCFrame.Position.Y, MobCollider.Position.Z))

                                if MobCollider ~= LastCollider or DistanceFromMob > 200 then
                                    if TeleportTween then
                                        TeleportTween:Cancel()
                                        TeleportTween = nil
                                    end

                                    PlayerRoot.CFrame = TargetCFrame
                                    LastCollider = MobCollider
                                else
                                    TeleportTween = TweenService:Create(PlayerRoot, TweenInfo.new((PlayerRoot.Position - MobCollider.Position).Magnitude / 70, Enum.EasingStyle.Linear), {CFrame = TargetCFrame})
                                    TeleportTween:Play()
                                end
                                if IsBoss and not TeleportMob:GetAttribute("T") then
                                    TeleportMob:SetAttribute("T", time())
                                end

                                if IsMobCamera and CurrentCamera.CameraSubject ~= TeleportMob then
                                    CurrentCamera.CameraSubject = TeleportMob
                                end
                            end
                        else
                            if TeleportTween then
                                TeleportTween:Cancel()
                                TeleportTween = nil
                            end
                        end
                        TeleportStandPart()
                        task.wait()
                    end
                end)
                if not Success then
                    SaveErrorToFile("MOB TELEPORT", Result)
                end
            end)
            task.spawn(function()
                local Success, Result = pcall(function()
                    for Part, PartData in TeleportParts do
                        if Part and Part.Parent then
                            Part.Size = Vector3.new(1, 1, 1)
                            Part.CanCollide = false
                        end
                    end
                    while SV.Autofarm do
                        for Part, PartData in TeleportParts do
                            if not SV.StopTeleportingParts then
                                if PartData.DontTeleport then
                                    continue
                                end
                                if Part.Parent and PartData.TouchPart.Parent then
                                    task.spawn(function()
                                        Part.Position = PlayerRoot.Position
                                        task.wait(0.1)
                                        Part.Position = PartData.OriginalLocation
                                    end)
                                else
                                    if not PartData.Regenerates then
                                        TeleportParts[Part] = nil
                                    end
                                end
                            end
                        end
                        task.wait()
                    end
                end)
                if not Success then
                    SaveErrorToFile("AUTO PROGRESS", Result)
                end
            end)
            task.spawn(function()
                local Success, Result = pcall(function()
                    local ShieldDungeons = {
                        16, 21, 38, 44, 52
                    }
                    local ShieldNames = {
                        "IceWall", "IgnisShield", "ZeroShield", "ShieldEgg", "EggShield"
                    }
                    if table.find(ShieldDungeons, ISV.MissionId) or SV.PartyRaidID == 14 then
                        while SV.Autofarm do
                            for Index, Shield in ShieldNames do
                                local CheckShield = Workspace:FindFirstChild(Shield)
                                if CheckShield then
                                    if CheckShield.Name == "ShieldEgg" or CheckShield.Name == "EggShield" then
                                        local ChangeEggName = CheckShield:WaitForChild("ShieldEgg", 1) or CheckShield:WaitForChild("Blade", 1)
                                        if ChangeEggName then
                                            ChangeEggName.Name = "Ring"
                                        end
                                    end
                                    local Ring = CheckShield:WaitForChild("Ring", 5)
                                    if Ring and Ring.Parent then
                                        local PlayerSize = GetPlayerSize() + (Ring.Size.Y / 2)
                                        local ShieldPosition = Vector3.new(Ring.Position.X, Ring.Position.Y + PlayerSize, Ring.Position.Z)
                                        TempStop = true
                                        CanTarget = false
                                        while CheckShield.Parent do
                                            PlayerRoot.CFrame = CFrame.new(ShieldPosition)
                                            task.wait()
                                        end
                                        TempStop = false
                                        CanTarget = true
                                    end
                                end
                                task.wait()
                            end
                            task.wait(.5)
                        end
                    end
                end)
                if not Success then
                    SaveErrorToFile("SHIELD TELEPORT", Result)
                end
            end)
        else
            PlayerRoot.CanCollide = true
            for Part, PartData in TeleportParts do
                if Part and Part.Parent then
                    Part.Size = PartData.OriginalSize
                    Part.CanCollide = PartData.OriginalCollision
                    Part.Position = PartData.OriginalLocation
                end
            end
            if SV.PlayerCamera and SV.PlayerCamera.Parent and PlayerRoot == SV.PlayerCamera.Parent then
                workspace.CurrentCamera.CameraSubject = SV.PlayerCamera
            else
                workspace.CurrentCamera.CameraSubject = PlayerRoot:WaitForChild("Part", math.huge)
            end
            SV.Autofarm = nil
        end
    end)
end
if not IsMainMenu then
    Toggles.CollectDropToggle:OnChanged(function(ChangedValue) -- collect drops
        if StringPlaceID == "6510868181" then
            return
        end
        if ChangedValue then
            SV.CollectDrops = true
            if SV.CanRequire and EF.Hook and EF.NewClosure then
                local rDrops = require(Drops)
                CreateHookOnFunction(rDrops.DropStarterpassExp, true)
                CreateHookOnFunction(rDrops.DropBattlepassExp, true)
                CreateHookOnFunction(rDrops.DropHealthOrb, true)
                CreateHookOnFunction(rDrops.SpawnCoinsLocal, true)
            end
            for CoinID, SpawnTime in SV.Drops do
                if time() < SpawnTime+120 then
                    Remotes:WaitForChild("Drops_CoinEvent", math.huge):FireServer(CoinID)
                end
            end
            table.clear(SV.Drops)
            CollectCoins()
        else
            SV.CollectDrops = false
            if SV.CanRequire and EF.Hook and EF.NewClosure then
                local rDrops = require(Drops)
                CreateHookOnFunction(rDrops.DropStarterpassExp, false)
                CreateHookOnFunction(rDrops.DropBattlepassExp, false)
                CreateHookOnFunction(rDrops.DropHealthOrb, false)
                CreateHookOnFunction(rDrops.SpawnCoinsLocal, false)
            end
        end
    end)
end
if IsDungeon then
    local PetKillaura
    local PetKillauraChanged
    Toggles.PetKillauraToggle:OnChanged(function(ChangedValue) -- use pet skill
        local TimeActivated = os.clock()
        PetKillauraChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= PetKillauraChanged then
            return
        end

        if ChangedValue then
            PetKillaura = true
            if SV.CanRequire then
                local Success, Result = pcall(function()
                    local UseSkill = Remotes:WaitForChild("PetSkills_UseSkill", math.huge)
                    local PetSkill = GetPlayerPet()

                    ConnectionTable["ConnectCharacter"] = PlayerCharacter.ChildAdded:Connect(function(NewChild)
                        if NewChild.Name == "PetData" then
                            PetSkill = GetPlayerPet()
                        end
                    end)

                    local CAttack = Remotes:WaitForChild("Combat_Attack", math.huge)
                    local AttackArgs = {
                        Ranged = function(Skill, AttackPosition)
                            CAttack:FireServer(Skill, AttackPosition, nil, AntiCheatNumber)
                        end,
                        Self = function()
                            UseSkill:FireServer(PlayerCharacter, PlayerRoot.Position)
                        end,
                        MobPosition = function(Skill, AttackPosition)
                            UseSkill:FireServer(PlayerCharacter, AttackPosition)
                        end
                    }
                    while PetKillaura and not KillSwitch do
                        for _, Attack in PetSkill.Skills do
                            if CurrentMob then
                                local AttackCooldown = Attack.Cooldown
                                if tick() - (Attack.LastUsed or 0) >= AttackCooldown+AddedDelay then
                                    local AttackType = Attack.Type
                                    local MobCollider = CurrentMob:FindFirstChild("Collider")
                                    if MobCollider then
                                        local AttackDistance = Attack.Distance
                                        local PlayerSurface = PlayerRoot:GetClosestPointOnSurface(MobCollider.Position)
                                        local MobSurface = MobCollider:GetClosestPointOnSurface(PlayerRoot.Position)
                                        local Distance = (PlayerSurface - MobSurface).Magnitude
                                        if Distance <= AttackDistance then
                                            local TpTime = CurrentMob:GetAttribute("T")
                                            if SV.Autofarm and IsBoss and not (TpTime and TpTime+0.2 < time()) then
                                                break
                                            end
                                            local FindAttackType = AttackArgs[AttackType]
                                            if FindAttackType then
                                                FindAttackType(Attack.Skill, MobSurface)
                                            else
                                                SV.PetKillaura = nil
                                                SaveErrorToFile("PET ATTACK TYPE", "invalid attack type or attack type not supported", AttackType)
                                                break
                                            end
                                            Attack.LastUsed = tick()
                                            if DelayPetAttacks then
                                                task.wait(DelayPetAttacks)
                                            end
                                        end
                                    end
                                end
                            end
                        end
                        task.wait(.1)
                    end
                end)
                if not Success then
                    local PetData = PlayerCharacter and PlayerCharacter:FindFirstChild("PetData")
                    if PetData and PetSkills and SV.CanRequire then
                        task.wait(.5)
                        local rPets = require(Pets)
                        local ItemName = PetData:GetAttribute("ItemName")
                        local PetName = ReplicatedStorage.PlayerEquips[PlayerName].Pet[ItemName]
                        local PetRef = rPets:GetPetSkillFromPetRef(PetName)
                        local SkillExists = PetSkills[tostring(PetRef)]
                        if SkillExists then
                            SkillExists = "pet skill is supported."
                        else
                            SkillExists = "skill data for " ..tostring(PetRef).. " was not found, skill not supported"
                        end
                        SaveErrorToFile("PET KILLAURA", Result, SkillExists)
                        return
                    end
                    SaveErrorToFile("PET KILLAURA", Result)
                end
            else
                local Success, Result = pcall(function()
                    local UseSkill = Remotes:WaitForChild("PetSkills_UseSkill", math.huge)
                    while PetKillaura and not KillSwitch do
                        if CurrentMob then
                            local MobCollider = CurrentMob:FindFirstChild("Collider", true)
                            if MobCollider then
                                UseSkill:FireServer(CurrentMob, MobCollider.Position)
                            end
                        end
                        task.wait(1)
                    end
                end)
                if not Success then
                    SaveErrorToFile("PET KILLAURA FALLBACK", Result)
                end
            end
        else
            DisconnectVariable("ConnectCharacter")
            PetKillaura = nil
        end
    end)
    local CheckForRejoin
    local RestartChanged
    Toggles.RestartStuckToggle:OnChanged(function(ChangedValue) -- stuck restart
        local TimeActivated = time()
        RestartChanged = TimeActivated
        CheckForCharacter()
        if not TimeActivated == RestartChanged then
            return
        end
        if ChangedValue then
            local Success, Result = pcall(function()
                ISV.LoggedDifficulty = GetDifficulty()
                CheckForRejoin = true
                RejoinLastDungeon(false)
                local CombatTimer = 0
                repeat
                    if not HoldForRealTime then
                        task.wait(1)
                        local Healthproperties = PlayerCharacter:FindFirstChild("HealthProperties", true)
                        local OutOfCombat = Healthproperties and Healthproperties:FindFirstChild("OutOfCombat", true)
                        if Healthproperties and OutOfCombat then
                            if OutOfCombat.Value == 0 then
                                CombatTimer += 1
                            else
                                CombatTimer = 0
                            end
                        end
                        if CombatTimer >= StuckDelay then
                            KillSwitch = true
                            task.wait(2)
                            task.spawn(function()
                                RejoinLastDungeon(true)
                            end)
                            break
                        end
                    end
                    task.wait(.1)
                until not CheckForRejoin
            end)
            if not Success then
                SaveErrorToFile("RESTART STUCK", Result)
            end
        else
            CheckForRejoin = nil
        end
    end)
    local DodgeAttacks
    local DodgeChanged
    Toggles.DodgeLethalToggle:OnChanged(function(ChangedValue) -- dodge lethal damage
        local TimeActivated = os.clock()
        DodgeChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= DodgeChanged then
            return
        end
        if ChangedValue and Class.Distance == "Melee" then
            DodgeAttacks = true 
            local Success, Result = pcall(function()
                local LingeringMobAttacks = {
                    "FireBase", "FireRings", "PoisonRings", "PoisonMeteorSpecialMedium", "MeteorSpecialSuper"
                }
                local LethalAttacks = {
                    ["DownwardIceFire"] = {AttackLength = 5.9, Delay = 1.5, AttackName = "downward ice"},
                    ["JumpAttack"] = {AttackLength = 2.5, Delay = 2, AttackName = "jump"},
                    ["Howl"] = {AttackLength = 4.2, Delay = 3.5, AttackName = "howl"},
                    ["DarkOrbAttack"] = {AttackLength = 8.2, Delay = 7.5, AttackName = "dark orb"},
                    ["WingFlap"] = {AttackLength = 6, Delay = 1, AttackName = "wing flap"},
                    ["Flyby"] = {AttackLength = 15, Delay = 0, AttackName = "flyby"},
                    ["FlybyX3"] = {AttackLength = 23, Delay = 0, AttackName = "long flyby"},
                    ["EggBomb"] = {AttackLength = 10, Delay = 3, AttackName = "egg bombs"},
                    ["SlamJump"] = {AttackLength = 5, Delay = 1, AttackName = 'slam jump'},
                    ["PrismSlam"] = {AttackLength = 3, Delay = 2, AttackName = "prism slam" }
                }
                while DodgeAttacks and not KillSwitch do
                    if CurrentMob then
                        local MobProperties = CurrentMob:FindFirstChild("MobProperties")
                        if MobProperties then
                            local CurrentAttack = MobProperties and MobProperties:FindFirstChild("CurrentAttack")
                            if (CurrentAttack and CurrentAttack.Value ~= "") then
                                local AttackToDodge = LethalAttacks[CurrentAttack.Value] or false
                                if AttackToDodge then
                                    DodgeCurrentAttack(AttackToDodge.Delay, AttackToDodge.AttackLength-AttackToDodge.Delay, AttackToDodge.AttackName)
                                end
                            end
                        end
                    end
                    for Index, LingeringAttack in LingeringMobAttacks do
                        local CheckAttack = Workspace:FindFirstChild(LingeringAttack)
                        if CheckAttack then
                            if Workspace:FindFirstChild("AnubisRing") or Workspace:FindFirstChild("AnubisRingPurple") then
                                break
                            end
                            local IsVane = Mobs:FindFirstChild("VaneAetherDragon") or Mobs:FindFirstChild("EVENTBOSSVane")
                            local SafeDistance = Vector3.new(PlayerRoot.Position.X+1000, PlayerRoot.Position.Y+1000, PlayerRoot.Position.Z)
                            if IsVane then
                                SafeDistance = Vector3.new(PlayerRoot.Position.X, PlayerRoot.Position.Y+1000, PlayerRoot.Position.Z)
                            end
                            TempStop = true
                            repeat
                                PlayerRoot.CFrame = CFrame.new(SafeDistance)
                                TeleportStandPart()
                                if not CheckAttack.Parent then
                                    break
                                end 
                                task.wait()
                            until not DodgeAttacks or KillSwitch
                            TempStop = false
                        end
                    end
                    task.wait(.1)
                end
            end)
            if not Success then
                SaveErrorToFile("DODGE LETHAL DAMAGE", Result)
            end
        else
            DodgeAttacks = nil
        end
    end)
end
if not IsMainMenu then
    Toggles.AutoPrestigeToggle:OnChanged(function(ChangedValue)
        if ChangedValue then
            if ISV.PlayerLevel >= 160 and ISV.PlayerPrestige < 4 then
                local Successm, Result = pcall(function()
                    KillSwitch = true
                    Library:Notify("Prestiging...", 5)
                    task.wait(5)
                    local PrestigeFile = "JDRS/" ..LocalPlayer.Name.. "_Prestige.txt"
                    if isfile(PrestigeFile) and StringPlaceID == "4310463616" and not IsDungeon then
                        delfile(PrestigeFile)
                        Remotes:WaitForChild("Profile_Prestige"):FireServer()
                        task.wait(1)
                        ReplayDungeonLoop(1, 5)
                    else
                        if not isfile(PrestigeFile) then
                            writefile(PrestigeFile, "haha txt file")
                        end
                        Remotes:WaitForChild("Teleport_TeleportToHub", math.huge):FireServer(13)
                    end
                end)
            end
        end
    end)
end
end -- for unloaded general tab
if not SV.EventTab then -- for unloaded event tab
SetGlobal("event stuff")
if IsDungeon then
    local CollectBuffs
    Toggles.CollectBuffToggle:OnChanged(function(ChangedValue)
        if ChangedValue then
            CollectBuffs = true
            while CollectBuffs and not KillSwitch do
                if SV.SelectedOrbs then
                    for Index, Orb in SV.SelectedOrbs do
                        if not Orb then
                            continue
                        end
                        local FoundOrb = Workspace:FindFirstChild(Orb)
                        if FoundOrb then
                            TeleportToOrb(FoundOrb)
                        end
                        task.wait()
                    end
                end
                task.wait(1)
            end
        else
            CollectBuffs = nil
        end
    end)
end
if not IsMainMenu then
    local ClaimingBattlepass = false
    Toggles.AutoClaimBattlepass:OnChanged(function(ChangedValue)
        if ChangedValue then
            if SV.CanRequire then
                if ClaimingBattlepass then
                    return
                else
                    ClaimingBattlepass = true
                end
                local rBattlepass = require(Battlepass)
                local RedeemedItem = Remotes:WaitForChild("Battlepass_RedeemedItem", math.huge)
                local RedeemItem = Remotes:WaitForChild("Battlepass_RedeemItem", math.huge)
                local HasPremiumTrack = Remotes:WaitForChild("Battlepass_HasPremium", math.huge):InvokeServer()

                local FreeClaimed, PaidClaimed = false
                local LastFree, LastPaid = -1

                if not HasPremiumTrack then
                    PaidClaimed = true
                end

                local function ClaimRank(Rank, Paid)
                    local ClaimStart = time() + 3
                    if not Paid then
                        repeat
                            if time() > ClaimStart then
                                break
                            end
                            RedeemItem:FireServer(Rank)
                            task.wait()
                        until RedeemedItem:InvokeServer(Rank)
                    else
                        repeat
                            if time() > ClaimStart then
                                break
                            end
                            RedeemItem:FireServer(Rank, true)
                            task.wait()
                        until RedeemedItem:InvokeServer(Rank, true)
                    end
                end

                repeat
                    local Tracks = { Remotes:WaitForChild("Battlepass_GetItemRanks", math.huge):InvokeServer() }
                    for Track = 1, #Tracks do
                        local Rank = Tracks[Track]
                        local NextTier = rBattlepass:FindNextItemTier(Tracks[Track])
                        if Track == 1 and not FreeClaimed then
                            if Rank == 0 or Rank ~= LastFree then
                                ClaimRank(NextTier)
                                LastFree = Rank
                            else
                                FreeClaimed = true
                            end
                        end
                        if Track == 2 and not PaidClaimed then
                            if Rank == 0 or Rank ~= LastPaid then
                                ClaimRank(NextTier, true)
                                LastPaid = Rank
                            else
                                PaidClaimed = true
                            end
                        end
                        task.wait()
                    end
                    task.wait()
                until FreeClaimed and PaidClaimed
                ClaimingBattlepass = false
            else
                Library:Notify("Your executor doesn't support this option")
            end
        end
    end)
end
end -- for unloaded event tab

if not SV.ClassesTab then -- for unloaded classes tab
SetGlobal("class tab functions")
if IsDungeon then
    local ClassBuffs
    Toggles.GeneralClassBuffToggle:OnChanged(function(ChangedValue) -- general class buffs
        if ChangedValue then
            ClassBuffs = true
            local AttackBuff = Remotes:WaitForChild("Skillset_DualWielder_AttackBuff", math.huge)
            local AggroDraw = Remotes:WaitForChild("Skillset_Guardian_AggroDraw", math.huge)
            while ClassBuffs and not KillSwitch do
                if IsAliveMobs > 0 then
                    AttackBuff:FireServer()
                    AggroDraw:FireServer()
                end
                task.wait(1)
            end
        else
            ClassBuffs = nil
        end
    end)
    local MolBuff
    Toggles.MoLBarrierToggle:OnChanged(function(ChangedValue) -- mol barrier
        if ChangedValue then
            local Success, Result = pcall(function()
                if SV.PlayerClass == "MageOfLight" then
                    MolBuff = true
                    local Barrier = Remotes:WaitForChild("Skillset_MageOfLight_Barrier")
                    while MolBuff do
                        if KillSwitch then
                            break
                        end
                        local AllPlayers = Players:GetChildren()
                        for _, BarrierAllPlayers in AllPlayers do
                            if BarrierAllPlayers.Name ~= PlayerName then
                                Barrier:FireServer(BarrierAllPlayers)
                            end
                            task.wait()
                        end
                        task.wait(2)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("MAGE OF LIGHT BARRIER", Result)
            end
        else
            MolBuff = nil
        end
    end)
    local DemonBuff
    Toggles.DemonBloodBindingToggle:OnChanged(function(ChangedValue) -- demon blood binding
        if ChangedValue then
            local Success, Result = pcall(function()
                if SV.PlayerClass == "Demon" then
                    DemonBuff = true
                    local BloodBinding = Remotes:WaitForChild("Skillset_Demon_BloodBinding")
                    while DemonBuff do
                        if KillSwitch then
                            break
                        end
                        if IsAliveMobs > 0 and CurrentMob then
                            BloodBinding:FireServer()
                            task.wait(7)
                        end
                        task.wait(.5)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("DEMON BLOOD BINDING", Result)
            end
        else
            DemonBuff = nil
        end
    end)
    local StormcallerBuff
    Toggles.StormcallerSuperchargeToggle:OnChanged(function(ChangedValue) -- stormcaller supercharge
        if ChangedValue then
            local Success, Result = pcall(function()
                if SV.PlayerClass == "Stormcaller" then
                    StormcallerBuff = true
                    local Supercharge = Remotes:WaitForChild("Skillset_Stormcaller_Supercharge", math.huge)
                    while StormcallerBuff do
                        if KillSwitch then
                            break
                        end
                        if IsAliveMobs > 0 then
                            Supercharge:FireServer()
                            task.wait(8)
                        end
                        task.wait(.5)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("STORMCALLER SUPERCHARGE", Result)
            end
        else
            StormcallerBuff = true
        end
    end)
end
end -- for unloaded classes tab

if not SV.DungeonsTab then -- for unloaded dungeons tab
SetGlobal("dungeon tab functions")
if IsDungeon then
    Toggles.CollectChestToggle:OnChanged(function(ChangedValue) -- collect chests
        if ChangedValue then
            if IsMissionOver() then
                CollectChests()
                return
            end
            if IsTower then
                SV.TowerChestDelay = true
                SV.CollectChests = true
                local OpenChest = Remotes:WaitForChild("Chests_OpenChest", math.huge)
                local CheckChest = Remotes:WaitForChild("Chests_CheckCondition", math.huge)
                for _, ChestID in SV.Chests do
                    if CheckChest:InvokeServer(ChestID) then
                        OpenChest:FireServer(ChestID)
                    end
                end
                table.clear(SV.Chests)
                CollectTowerChests()
            else
                SV.CollectDungeonChest = true
            end
        else
            DisconnectVariable("ConnectChests")
            SV.CollectDungeonChest = nil
            SV.TowerChestDelay = nil
        end
    end)
    Toggles.HighestDungeonToggle:OnChanged(function(ChangedValue)
        if ChangedValue then
            task.spawn(EquipNewItemAdded)
            SV.AutoLeveling = true
            if IsMissionOver() then
                ClaimAllQuests()
            end
        else
            DisconnectVariable("ConnectEquipNewItems")
            EquipInProgress = 0
            SV.AutoLeveling = nil
        end
    end)
    Toggles.ReplayMissionToggle:OnChanged(function(ChangedValue) -- replay dropdown
        if ChangedValue then
            SV.ReplayMission = true
            if IsMissionOver() then
                RestartDungeon()
                return
            end
        else
            SV.ReplayMission = nil
        end
    end)
    Toggles.ReplayInfiniteTowerToggle:OnChanged(function(ChangedValue) -- replay inf tower
        if ChangedValue then
            local ReplicateTowerFloor = ReplicatedStorage:FindFirstChild("ReplicateTowerFloor")
            if ReplicateTowerFloor then
                ConnectionTable["ConnectInfTower"] = ReplicateTowerFloor.Changed:Connect(function(NewFloor)
                    if (NewFloor >= RestartAtFloor+1) then
                        Library:Notify("Sending restart")
                        RestartDungeon(true)
                    end
                end)
            end
            if GetLives() == 0 then
                RestartDungeon(true)
            end
        else
            DisconnectVariable("ConnectInfTower")
        end
    end)
end
end -- for unloaded dungeons tab

if not SV.GuildTab then
SetGlobal("guild tab functions")
if IsDungeon then
    local GuildWait
    local PreviousWaitPosition
    local WaitNotification
    local WaitChanged
    Toggles.WaitTimeToggle:OnChanged(function(ChangedValue) -- wait for legit time
        local TimeActivated = os.clock()
        WaitChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= WaitChanged then
            return
        end

        if ChangedValue then
            GuildWait = true
            local GuildTimePassed = 0
            local Success, Result = pcall(function()
                local DungeonWaitTime = 120
                for DungeonIndex, Dungeon in SV.DungeonListTable do
                    if Dungeon.DungeonID == ISV.MissionId then
                        DungeonWaitTime = Dungeon.DungeonDelay
                        break
                    end
                end

                local MissionStart = Workspace:FindFirstChild("MissionStart", true)
                local StartGateTime = 0
                if MissionStart then
                    MissionStart:PivotTo(CFrame.new(PlayerRoot.Position))
                    StartGateTime = 5
                end

                HoldForRealTime = true
                task.wait(.2)
                local GuildWaitPosition = Vector3.new(PlayerRoot.Position.X+25000, PlayerRoot.Position.Y+25000, PlayerRoot.Position.Z)
                local PreviousWaitPosition = PlayerRoot.Position
                PlayerRoot.CFrame = CFrame.new(GuildWaitPosition)
                TeleportStandPart()
                local TimeToWait = DungeonWaitTime + (SV.AddedGuildTime or 0) + StartGateTime
                WaitNotification = Library:Notify("Waiting for legit time", TimeToWait)

                local StartTime = time() + TimeToWait
                while GuildWait do
                    if KillSwitch then
                        break
                    end
                    if time() >= StartTime then
                        HoldForRealTime = false
                        PlayerRoot.CFrame = CFrame.new(PreviousWaitPosition)
                        TeleportStandPart()
                        PreviousWaitPosition = nil
                        break
                    end
                    PlayerRoot.CFrame = CFrame.new(GuildWaitPosition)
                    TeleportStandPart()
                    task.wait(.1)
                end
            end)
            if not Success then
                SaveErrorToFile("WAIT FOR LEGIT TIME", Result)
            end
        else
            GuildWait = nil
            HoldForRealTime = false
            if WaitNotification then
                WaitNotification:Destroy()
                WaitNotification = nil
            end
            if PreviousWaitPosition then
                PlayerRoot.CFrame = CFrame.new(PreviousWaitPosition)
            end
            TeleportStandPart()
        end
    end)
    Toggles.DoAllDungeonsToggle:OnChanged(function(ChangedValue) -- do all dungeons
        if ChangedValue then
            Library:Notify("Doing all dungeons", 10)
            SV.DoingGuildDungeon = true
        else
            SV.DoingGuildDungeon = nil
        end
    end)
    local InfNotification
    local InfDelay
    local InfWait
    local InfChanged
    Toggles.DelayInfFloorToggle:OnChanged(function(ChangedValue) -- delay inf tower
        local TimeActivated = os.clock()
        InfChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= InfChanged then
            return
        end

        if ChangedValue then
            InfWait = true
            InfDelay = InfDelay or 25
            local Success, Result = pcall(function()
                if ISV.MissionId == 38 then
                    local DungeonScript = ReplicatedStorage:WaitForChild("MissionScripts", math.huge):FindFirstChildWhichIsA("ModuleScript")
                    if DungeonScript then
                        local IsBossFloor
                        ConnectionTable["UpdateMobTracker"] = DungeonScript:WaitForChild("UpdateMobTracker", math.huge).OnClientEvent:Connect(function(KilledMobs, TotalMobs)
                            if TotalMobs < 10 then
                                IsBossFloor = true
                            else
                                IsBossFloor = false
                                return
                            end
                            if KilledMobs == TotalMobs then
                                InfDelay = InfDelay + SV.IncrementInfiniteDelay
                                IsBossFloor = false
                            end
                        end)
                        ConnectionTable["UpdateTowerFloor"] = DungeonScript:WaitForChild("UpdateTowerFloor", math.huge).OnClientEvent:Connect(function(CurrentFloor)
                            HoldForRealTime = true
                            local GuildWaitPosition = Vector3.new(PlayerRoot.Position.X+25000, PlayerRoot.Position.Y+25000, PlayerRoot.Position.Z)
                            local PreviousPosition = PlayerRoot.Position
                            InfNotification = Library:Notify("Delaying floor", InfDelay)

                            local StartTime = time() + InfDelay
                            while InfWait do
                                if KillSwitch then
                                    break
                                end
                                if IsBossFloor or time() >= StartTime then
                                    if InfNotification then
                                        InfNotification:Destroy()
                                        InfNotification = nil
                                    end
                                    HoldForRealTime = false
                                    PlayerRoot.CFrame = CFrame.new(PreviousPosition)
                                    TeleportStandPart()
                                    break
                                end
                                PlayerRoot.CFrame = CFrame.new(GuildWaitPosition)
                                TeleportStandPart()
                                task.wait(.1)
                            end
                            HoldForRealTime = false
                        end)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("DELAY INF TOWER FLOORS", Result)
            end
        else
            if InfNotification then
                InfNotification:Destroy()
                InfNotification = nil
            end
            InfWait = nil
            DisconnectVariable("UpdateMobTracker")
            DisconnectVariable("UpdateTowerFloor")
        end
    end)
    Toggles.GuildQuestToggle:OnChanged(function(ChangedValue) -- claim guild quests
        if ChangedValue then
            if not SV.CanRequire then
                Library:Notify("Your executor doesn't support claiming guild quests", 3)
                return
            end
            SV.ClaimGuildQuests = true
        else
            SV.ClaimGuildQuests = nil
        end
    end)
end
end -- for unloaded guild tab

if not SV.ShopsTab then -- for unloaded shops tab
SetGlobal("shop tab functions")
if not IsMainMenu then
    local AutoHatch
    Toggles.AutoHatchEggToggle:OnChanged(function(ChangedValue) -- auto hatch eggs
        if ChangedValue then
            AutoHatch = true
            local Success, Result = pcall(function()
                local PetSlot = ReplicatedStorage.PlayerEquips[PlayerName].Pet
                local EquipItem = Remotes:WaitForChild("Inventory_EquipItem", math.huge)
                local Hatch = Remotes:WaitForChild("Pets_Hatch", math.huge)
                local pItems = ProfileInventory.Items
                repeat
                    local TableReference = SV.SelectedEggItem
                    if not TableReference then
                        Library:Notify("No egg is selected", 3)
                        task.wait(3)
                        if not AutoHatch then
                            break
                        end
                        continue
                    end
                    local CurrentPet = PetSlot:FindFirstChildWhichIsA("Folder")
                    if CurrentPet and string.find(CurrentPet.Name, "Egg") then
                        task.wait(.1)
                        continue
                    end
                    task.wait(SV.HatchDelay)
                    if not BuyFromEggShop(TableReference.CurrencyType, TableReference.InternalName, TableReference.CoinPrice, TableReference.VisualName) then
                        Library:Notify("You do not have enough gold", 3)
                        task.wait(3)
                        if not AutoHatch then
                            break
                        end
                        continue
                    else
                        local BoughtEgg = pItems:WaitForChild(TableReference.InternalName, 5)
                        if BoughtEgg then
                            EquipItem:FireServer(BoughtEgg, PetSlot)
                            repeat
                                task.wait()
                            until PetSlot:FindFirstChild(TableReference.InternalName)
                            Hatch:FireServer()
                        end
                    end
                    task.wait()
                until not AutoHatch
            end)
            if not Success then
                SaveErrorToFile("AUTO HATCH", Result)
            end
        else
            AutoHatch = nil
        end
    end)
    local AutoHatchInventory
    Toggles.AutoHatchInventoryEggToggle:OnChanged(function(ChangedValue) -- auto hatch inventory  eggs
        if ChangedValue then
            AutoHatchInventory = true
            local Success, Result = pcall(function()
                local EggTable = {}
                for Index, Egg in SV.EggList do
                    EggTable[Egg] = true
                end
                local PetSlot = ReplicatedStorage.PlayerEquips[PlayerName].Pet
                local EquipItem = Remotes:WaitForChild("Inventory_EquipItem", math.huge)
                local Hatch = Remotes:WaitForChild("Pets_Hatch", math.huge)
                local pItems = ProfileInventory.Items
                repeat
                    local CurrentPet = PetSlot:FindFirstChildWhichIsA("Folder")
                    if CurrentPet and CurrentPet.Parent and EggTable[CurrentPet.Name] then
                        task.wait(.1)
                        continue
                    end
                    local HatchingPet = false
                    for Index, Item in pItems:GetChildren() do
                        if Item and Item.Parent and EggTable[Item.Name] then
                            task.wait(SV.HatchDelay)
                            EquipItem:FireServer(Item, PetSlot)
                            local EquippedEgg = PetSlot:WaitForChild(Item.Name, 5)
                            if EquippedEgg then
                                task.wait(.5)
                                Hatch:FireServer()
                                task.wait(5)
                                HatchingPet = true
                                break
                            end
                        end
                    end
                    if not HatchingPet then
                        task.wait(5)
                    end
                    task.wait()
                until not AutoHatchInventory
            end)
            if not Success then
                SaveErrorToFile("INVENTORY HATCH", Result)
            end
        else
            AutoHatchInventory = nil
        end
    end)
end
end -- for unloaded shops tab
task.wait()

if not SV.MiscellaneousTab then -- for unloaded miscellaneous tab
SetGlobal("misc tab functions")
if IsDungeon then
    SV.PlayerCamera = Camera.CameraSubject
    local CameraChanged
    Toggles.MobCameraToggle:OnChanged(function(ChangedValue) -- mob camera
        local TimeActivated = os.clock()
        CameraChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= CameraChanged then
            return
        end

        if ChangedValue then
            task.spawn(function()
                Toggles.NoclipCameraToggle:SetValue(true)
            end)
            IsMobCamera = true
        else
            IsMobCamera = false
            task.wait(.1)
            if SV.PlayerCamera and SV.PlayerCamera.Parent and PlayerRoot == SV.PlayerCamera.Parent then
                workspace.CurrentCamera.CameraSubject = SV.PlayerCamera
            else
                workspace.CurrentCamera.CameraSubject = PlayerRoot:WaitForChild("Part", math.huge)
            end
        end
    end)
end
if not IsMainMenu then
    Toggles.DamageNumbersToggle:OnChanged(function(ChangedValue) -- remove damage numbers
        if SV.CanRequire and EF.Hook and EF.ClearHook and EF.NewClosure and EF.CheckHook then
            local Success, Result = pcall(function()
                local RenderDamageNumber = require(Effects).RenderDamageNumber
                if ChangedValue then
                    CreateHookOnFunction(RenderDamageNumber, true)
                else
                    CreateHookOnFunction(RenderDamageNumber, false)
                end
            end)
            if not Success then
                SaveErrorToFile("REMOVE DAMAGE NUMBERS", Result)
            end
        else
            local Success, Result = pcall(function()
                local DamageNumbers = Remotes:FindFirstChild("Effects_RenderDamageNumber")
                if ChangedValue and DamageNumbers then
                    SV.RemovedDamageNumbers = true
                    DamageNumbers:Destroy()
                    DamageNumbers = nil
                else
                    if SV.RemovedDamageNumbers then
                        Library:Notify("Rejoin to see damage numbers", 5)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("REMOVE DAMAGE NUMBERS FALLBACK", Result)
            end
        end
    end)
    Toggles.DamageFlashToggle:OnChanged(function(ChangedValue) -- hide damage flash
        if ChangedValue then
            SharedAssets.Combat.HitHighlight.Enabled = false
        else
            SharedAssets.Combat.HitHighlight.Enabled = true
        end
    end)
    Toggles.DeathEffectToggle:OnChanged(function(ChangedValue) -- hide damage flash
        if SV.CanRequire and EF.Hook and EF.ClearHook and EF.NewClosure and EF.CheckHook then
            local Success, Result = pcall(function()
                local DoEffect = require(Effects).DoEffect
                if ChangedValue then
                    local OldFunction
                    OldFunction = EF.Hook(DoEffect, EF.NewClosure(function(a, Effect, ...)
                        if Effect == "DeathEffect" then
                            return
                        else
                            return OldFunction(a, Effect, ...)
                        end
                    end))
                else
                    CreateHookOnFunction(DoEffect, false)
                end
            end)
            if not Success then
                SaveErrorToFile("REMOVE DEATH EFFECTS", Result)
            end
        else
            local Success, Result = pcall(function()
                if ChangedValue then
                    SV.RemovedDeathEffects = true
                    local DeathEffect = Effects.EffectScripts:FindFirstChild("DeathEffect")
                    if DeathEffect then
                        DeathEffect:Destroy()
                        DeathEffect = nil
                    end
                else
                    if SV.RemovedDeathEffects then
                        Library:Notify("Rejoin to see death effects", 5)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("REMOVE DEATH EFFECTS FALLBACK", Result)
            end
        end
    end)
    Toggles.KnockdownToggle:OnChanged(function(ChangedValue) -- stops player from being knocked down
        if SV.CanRequire and EF.Hook and EF.ClearHook and EF.NewClosure and EF.CheckHook then
            local Success, Result = pcall(function()
                local Knockdown = require(Client.Actions).Knockdown
                if ChangedValue then
                    CreateHookOnFunction(Knockdown, true)
                else
                    CreateHookOnFunction(Knockdown, false)
                end
            end)
            if not Success then
                SaveErrorToFile("DISABLE KNOCKDOWN", Result)
            end
        end
    end)
end
if IsWorld then
    Toggles.WaystoneToggle:OnChanged(function(ChangedValue)
        local Success, Result = pcall(function()
            if ChangedValue then
                SV.WaystonesHidden = true
                ConnectionTable["ConnectWaystones"] = PlayerGui.ChildAdded:Connect(function(AddedChild)
                    if AddedChild.Parent and AddedChild.Name == "WaystoneDiscoveryIcon" then
                        AddedChild.PlayerToHideFrom = LocalPlayer
                    end
                end)
                for Index, Gui in PlayerGui:GetChildren() do
                    if Gui.Name == "WaystoneDiscoveryIcon" then
                        Gui.PlayerToHideFrom = LocalPlayer
                    end
                end
            else
                if SV.WaystonesHidden then
                    DisconnectVariable("ConnectWaystones")
                    for Index, Gui in PlayerGui:GetChildren() do
                        if Gui.Parent and Gui.Name == "WaystoneDiscoveryIcon" then
                            Gui.PlayerToHideFrom = nil
                        end
                    end
                    SV.WaystonesHidden = nil
                end
            end
        end)
        if not Success then
            SaveErrorToFile("HIDE WAYSTONES", Result)
        end
    end)
end
if IsDungeon then
    Toggles.ShowEndTimeToggle:OnChanged(function(ChangedValue) -- display end time
        if ChangedValue then
            SV.ShowTime = true
            if IsMissionOver() then
                Library:Notify("Completed in " ..SV.DungeonCompletionTime)
            end
        else
            SV.ShowTime = nil
        end
    end)
end
if IsDungeon then
    local ProfilerGui
    local ShowAccountInfo
    Toggles.ProfilerToggle:OnChanged(function(ChangedValue) -- show account information
        if ChangedValue then
            ShowAccountInfo = true
            ProfilerGui = Library:AddDraggableLabel("account info")
            ProfilerGui:SetVisible(true)
            local Gold = PlayerProfile:WaitForChild("Currency"):WaitForChild("Gold")
            local Success, Result = pcall(function()
                repeat
                    ProfilerGui:SetText(string.format(
                        "Account: %*\nClass: %*\nGold %*\nCrystals: %*\nGuild: %*",
                        LocalPlayer.Name.. " ("..LocalPlayer.DisplayName..")",
                        ClassSkills[SV.PlayerClass].DisplayName,
                        FormatNumber(Gold.Value),
                        FormatNumber(Remotes.Crystals_GetCrystals:InvokeServer()),
                        GetGuild(LocalPlayer)
                    ))
                    task.wait(5)
                until not ShowAccountInfo
            end)
            if not Success then
                local GuildLog = GetGuild(LocalPlayer)
                if GuildLog ~= "❌" then
                    GuildLog = "Yes"
                else
                    GuildLog = "No"
                end
                SaveErrorToFile("DISPLAY ACCOUNT INFO", Result, string.format(
                    "P: %*, C: %*, G: %*, C: %*, G: %*",
                    string.gsub(LocalPlayer:GetFullName(), PlayerName, "LocalPlayer"),
                    ClassSkills[SV.PlayerClass].DisplayName,
                    FormatNumber(Gold.Value),
                    FormatNumber(Remotes.Crystals_GetCrystals:InvokeServer()),
                    GuildLog
                ))
            end
        else
            if ProfilerGui then
                ProfilerGui:Destroy()
                ProfilerGui = nil
            end
            ShowAccountInfo = nil
        end
    end)
end
local PreventAfk
Toggles.AFKToggle:OnChanged(function(ChangedValue) -- anti afk
    if ChangedValue then
        PreventAfk = true
        while PreventAfk do
            if KillSwitch then
                break
            end
            VirtualUser:CaptureController()
            VirtualUser:ClickButton2(Vector2.new(0, 0))
            task.wait(10)
        end
    else
        PreventAfk = nil
    end
end)
if IsMainMenu then
    Toggles.MainMenuPlay:OnChanged(function(ChangedValue)
        if ChangedValue then
            if firesignal then
                local PlayButton = PlayerGui:WaitForChild("MainMenuGui", math.huge):WaitForChild("Main", math.huge):WaitForChild("Play", math.huge):WaitForChild("Play", math.huge)
                if not ChangedValue then
                    return
                end
                while not (KillSwitch or ScriptUnloaded) do
                    firesignal(PlayButton.MouseButton1Click)
                    task.wait(.5)
                end
            else
                Library:Notify("Your executor doesn't support this option")
            end
        end
    end)
end
if IsWorld then
    Toggles.AutoJoinDungeon:OnChanged(function(ChangedValue)
        if ChangedValue and ISV.PlayerLevel == 175 then
            ReplayDungeonLoop(1005, 6)
        end
    end)
end
if not IsMainMenu then
    Toggles.RemoveOtherPlayersToggle:OnChanged(function(ChangedValue) -- remove other players
        if ChangedValue then
            local CharacterFolder = Workspace:FindFirstChild("Characters")
            for _, CheckCharacters in CharacterFolder:GetChildren() do
                if CheckCharacters.Name == PlayerName then continue end

                CheckCharacters:Destroy()
                CheckCharacters = nil
            end
            ConnectionTable["ConnectCharacterFolder"] = CharacterFolder.ChildAdded:Connect(function(AddedCharacter)
                task.wait(0.1)
                if AddedCharacter.Name == PlayerName then return end
                
                AddedCharacter:Destroy()
                AddedCharacter = nil
            end)
        else
            DisconnectVariable("ConnectCharacterFolder")
        end
    end)
    Toggles.MobESPToggle:OnChanged(function(ChangedValue) -- mob esp
        if ChangedValue then
            for _, Mob in Mobs:GetChildren() do
                if Mob then
                    local Highlight = Instance.new("Highlight")
                    Highlight.FillTransparency = 0
                    Highlight.Parent = Mob
                end
            end
            ConnectionTable["ConnectMobFolder"] = Mobs.ChildAdded:Connect(function(NewMob)
                if NewMob then
                    local Highlight = Instance.new("Highlight")
                    Highlight.FillTransparency = 0
                    Highlight.Parent = NewMob
                end
            end)
        else
            DisconnectVariable("ConnectMobFolder")
            for _, MobFolder in Mobs:GetChildren() do
                local MobHighlight = MobFolder and MobFolder:FindFirstChild("Highlight", true)
                if MobHighlight then
                    MobHighlight:Destroy()
                    MobHighlight = nil
                end
            end
        end
    end)
    Toggles.NoclipCameraToggle:OnChanged(function(ChangedValue) -- noclip camera
        if ChangedValue then
            LocalPlayer.DevCameraOcclusionMode = Enum.DevCameraOcclusionMode.Invisicam
        else
            LocalPlayer.DevCameraOcclusionMode = Enum.DevCameraOcclusionMode.Zoom
        end
    end)
    local JumpChanged
    Toggles.DisableAutoJumpToggle:OnChanged(function(ChangedValue) -- disable auto jump
        local TimeActivated = os.clock()
        JumpChanged = CheckForCharacter(TimeActivated)
        if TimeActivated ~= JumpChanged then
            return
        end
        if ChangedValue then
            PlayerCharacter.Humanoid.AutoJumpEnabled = false
        end
    end)
    ISV.RenderingScreen = MakeGuiElement("ScreenGui", {
        IgnoreGuiInset = true,
        DisplayOrder = -1,
    })
        MakeGuiElement("Frame", {
            AnchorPoint = Vector2.new(0.5, 0.5),
            Position = UDim2.new(0.5, 0, 0.5, 0),
            BackgroundColor3 = Color3.fromRGB(0, 0, 0),
            Size = UDim2.new(1, 0, 2, 0),
            Parent = ISV.RenderingScreen
        })
        MakeGuiElement("TextLabel", {
            AnchorPoint = Vector2.new(0.5, 0.5),
            Position = UDim2.new(0.5, 0, 0.5, 0),
            BackgroundTransparency = 1,
            BackgroundColor3 = Color3.fromRGB(0, 0, 0),
            Size = UDim2.new(0.5, 0, 0.1, 0),
            TextColor3 = Color3.new(255, 255, 255),
            FontFace = Font.new("rbxasset://fonts/families/FredokaOne.json"),
            Text = "3d rendering disabled",
            TextScaled = true,
            Parent = ISV.RenderingScreen
        })
    Toggles.DisableRenderingToggle:OnChanged(function(ChangedValue) -- disable rendering
        if IsDungeon then
            local Success, Result = pcall(function()
                if ChangedValue then
                    RunService:Set3dRenderingEnabled(false)
                    ISV.RenderingScreen.Parent = EF.HideGui() or CoreGui
                else
                    RunService:Set3dRenderingEnabled(true)
                    ISV.RenderingScreen.Parent = nil
                end
            end)
            if not Success then
                SaveErrorToFile("DISABLE RENDERING", Result)
            end
        end
    end)
    local SetUpFakeModel
    Toggles.PreventMobToggle:OnChanged(function(ChangedValue) -- stop rendering new things
        if SV.CanRequire and EF.Hook and EF.ClearHook and EF.NewClosure and EF.CheckHook then
            local Success, Result = pcall(function()
                local GetModel = require(ModelProvider).GetModel
                if ChangedValue then
                    local Shockball = SharedAssets.Effects.Models.Shockball
                    if not SetUpFakeModel then
                        if not Shockball:FindFirstChild("HumanoidRootPart") then
                            Shockball.Part.Color = Color3.fromRGB(255, 0, 0)
                            Shockball.Part.Material = "Neon"
                            Shockball.Part.Transparency = 0.7
                            Shockball.Part.Name = "HumanoidRootPart"
                        end
                        SetUpFakeModel = true
                    end

                    local ModelHook
                    ModelHook = EF.Hook(GetModel, EF.NewClosure(function(self, model)
                        if not string.find(model, "Pet") then
                            return Shockball:Clone()
                        else
                            return ModelHook(self, model)
                        end
                    end))
                else
                    CreateHookOnFunction(GetModel, false)
                end
            end)
            if not Success then
                SaveErrorToFile("PREVENT MODELS FROM LOADING", Result)
            end
        else
            local Success, Result = pcall(function()
                local GetModel = Remotes:FindFirstChild("ModelProvider_GetModel")
                if ChangedValue and GetModel then
                    SV.RemovedModels = true
                    GetModel:Destroy()
                    GetModel = nil
                else
                    if SV.RemovedModels then
                        Library:Notify("Rejoin to see assets", 5)
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("PREVENT MODELS FROM LOADING FALLBACK", Result)
            end
        end
    end)
    Toggles.PreventEffectsToggle:OnChanged(function(ChangedValue)
        if SV.CanRequire and EF.Hook and EF.ClearHook and EF.NewClosure and EF.CheckHook then
            local Success, Result = pcall(function()
                local rEffects = require(Effects)
                if ChangedValue then
                    CreateHookOnFunction(rEffects.MakeProjectile, true)
                    CreateHookOnFunction(rEffects.DoEffect, true)
                    CreateHookOnFunction(rEffects.PlayAt, true)
                    CreateHookOnFunction(rEffects.EmitAt, true)
                else
                    CreateHookOnFunction(rEffects.MakeProjectile, false)
                    CreateHookOnFunction(rEffects.DoEffect, false)
                    CreateHookOnFunction(rEffects.PlayAt, false)
                    CreateHookOnFunction(rEffects.EmitAt, false)
                end
            end)
            if not Success then
                SaveErrorToFile("PREVENT NEW EFFECTS", Result)
            end
        else
            Library:Notify("Your executor doesn't support this option", 5)
        end
    end)
end
end -- for unloaded miscellaneous tab

if not SV.DiscordTab then
SetGlobal("discord ping type")
if IsDungeon then
    Toggles.ClassPingToggle:OnChanged(function(ChangedValue)
        if ChangedValue then
            local Success, Result = pcall(function()
                local MasteryClassTable = {
                    ["IcefireMage"] = { MasteryRequirement = 400, MasteryDisplayName = "Stormcaller" },
                    ["MageOfLight"] = { MasteryRequirement = 350, MasteryDisplayName = "Mage of Shadows" },
                    ["Archer"] = { MasteryRequirement = 200, MasteryDisplayName = "Hunter" },
                    ["Dragoon"] = { MasteryRequirement = 10000, MasteryDisplayName = "Leviathan" },
                    ["Guardian"] = { MasteryRequirement = 7500, MasteryDisplayName = "Starbreaker" },
                    ["Demon"] = { MasteryRequirement = 150, MasteryDisplayName = "Necromancer" }
                }
                local Masteries = PlayerProfile:FindFirstChild("Masteries")
                if Masteries then
                    local CurrentClass = Masteries:FindFirstChild(SV.PlayerClass)
                    local MasteryClass = MasteryClassTable[SV.PlayerClass]
                    if (CurrentClass and MasteryClass and CurrentClass.Value >= MasteryClass.MasteryRequirement) then
                        PingOnceUnlocked(MasteryClass.MasteryDisplayName)
                        TempStop = true
                        SV.Killaura = nil
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("MASTERY CLASS UNLOCK", Result)
            end
        end
    end)
end
end -- for unloaded discord tab

SetGlobal("getting mission id")
if IsDungeon then
    MissionObjects = Workspace:WaitForChild("MissionObjects", math.huge)
    ISV.MissionId = WaitForAttribute(Workspace, "MissionId")
end 

SetGlobal("nightmare dungeon check")
do
    if IsDungeon and (ISV.MissionId > 1004 and ISV.MissionId < 1008 ) then
        SV.IsNightmareDungeon = true
    end
end

SetGlobal("get attack data")
if IsDungeon and not KillSwitch then
    local Success, Result = pcall(function()
        ClassSkills = SaveScriptToFiles("https://raw.githubusercontent.com/Veltrinix/oldobsidianlibrary/main/c", "C", 5.4)
        PetSkills = SaveScriptToFiles("https://raw.githubusercontent.com/Veltrinix/oldobsidianlibrary/main/p", "P", 4.5)
        if ClassSkills and PetSkills then
            Class = GetPlayerClass()
            if Class ~= nil then
                local ClassRange = Class.Distance
                if ClassRange == "Ranged" then
                    Xdistance = 20
                    Ydistance = 50
                elseif ClassRange == "Melee" then
                    Xdistance = 13
                    Ydistance = 8
                end
            end
        else
            warn(string.format(
                "JDRS: Unable to get skill data. Check variables below\nClass data: %*\nPet data: %*",
                ClassSkills and "Yes" or "No", PetSkills and "Yes" or "No"
            ))
        end
    end)
    if not Success then
        SaveErrorToFile("ATTACK DATA", Result, SV.PlayerClass)
    end
end

SetGlobal("require() check")
if not IsMainMenu then
    local Success, Result = pcall(function()
        require(LocalPlayer:WaitForChild("PlayerScripts", math.huge):WaitForChild("PlayerModule", math.huge))
    end)
    if not Success then
        SV.CanRequire = nil
        print("JDRS: executor doesn't support require(). Applying fixes.")
    else
        SV.CanRequire = true
    end
end

SetGlobal("removing purchase prompt")
task.spawn(function()
    pcall(function()
        if IsDungeon and CoreGui and CoreGui:FindFirstChild("PurchasePromptApp") then
            CoreGui:FindFirstChild("PurchasePromptApp"):Destroy()
        end
    end)
end)

SetGlobal("dungeon specific checks")
if IsDungeon then
    task.spawn(function()
        CheckForCharacter()
        task.spawn(function()
            local Success, Result = pcall(function()
                local SaveRemote = {
                    ["Mob_EVENTBOSSCupidZeus_ButtonSmash"] = true,
                    ["Mob_EVENTBOSSEasterBunny_ChallengeFloorPattern"] = true,
                    ["Mob_EVENTBOSSEasterBunny_RequestGiantEggChallengeFloorIntro"] = true,
                    ["Mob_EVENTBOSSEasterBunny_DoGiantEgg"] = true,
                    ["Mob_EVENTBOSSUndeadVane_ResurrectShake"] = true,
                    ["Mob_FallenKingMinion_OnCureFountain"] = true
                }
                for Index, Descednant in Remotes:GetChildren() do
                    if Descednant:IsA("RemoteEvent") and string.find(Descednant.Name, "Mob_") then
                        if SaveRemote[Descednant.Name] then
                            continue
                        end
                        local CloneRemote = Descednant:Clone()
                        CloneRemote.Parent = Descednant.Parent
                        Descednant:Destroy()
                        Descednant = nil
                    end
                end
            end)
            if not Success then
                SaveErrorToFile("CLIENT SIDE DAMAGE", Result)
            end
        end)
        task.spawn(function()
            if ISV.MissionId == 49 then
                local Success, Result = pcall(function()
                    if SV.CanRequire and debug and getupvalue then
                        local ChestScript = debug.getupvalue(require(Chests).Start, 12)
                        local OpenChest = Remotes:WaitForChild("Chests_OpenChest", math.huge)
                        repeat
                            for ChestKey, Useless in ChestScript do
                                OpenChest:FireServer(ChestKey)
                            end
                            task.wait(.1)
                        until KillSwitch
                    else
                        local ChestNames = {
                            "RaidChestBlue", "RaidChestGold", "RaidChestSilver"
                        }
                        repeat
                            for Index, ChestName in ChestNames do
                                local Chest = Workspace:FindFirstChild(ChestName)
                                if Chest and Chest.Parent then
                                    Chest:PivotTo(CFrame.new(PlayerRoot.Position))
                                end
                                task.wait()
                            end
                            task.wait(.1)
                        until KillSwitch
                    end
                end)
                if not Success then
                    SaveErrorToFile("STARTER DUNGEON CHESTS", Result)
                end
            end
        end)
        task.spawn(function()
            if ISV.MissionId == 54 then
                local IntroDone = Remotes:WaitForChild("Tutorial_IntroDone", math.huge)
                repeat
                    IntroDone:FireServer()
                    task.wait()
                until KillSwitch
            end
            if ISV.MissionId == 53 then
                task.spawn(function()
                    local ObbyEnd = MissionObjects:WaitForChild("Room2", math.huge):WaitForChild("ObbyEnd", math.huge):WaitForChild("VFX", math.huge).Position
                    local Teleporting
                    local ObjectiveMessage = ReplicatedStorage:WaitForChild("ObjectiveMessage", math.huge)
                    local MaxJudgementThreshold = 40
                    if not SV.IsRanged then
                        MaxJudgementThreshold = 60
                    end
                    ConnectionTable["ConnectObjectiveMessage"] = ObjectiveMessage.Changed:Connect(function(NewString)
                        if Teleporting then
                            return
                        end
                        if not string.find(NewString, "together") then
                            return
                        end
                        Teleporting = true
                        task.wait(0.5)
                        local Sword = MissionObjects:WaitForChild("Room1", math.huge):WaitForChild("Sword", math.huge):WaitForChild("Blade", math.huge).Position
                        if Sword then
                            local TeleportTimer = time() + 1
                            repeat
                                PlayerRoot.CFrame = CFrame.new(Sword)
                                task.wait()
                            until time() > TeleportTimer or not SV.Autofarm
                        end
                        local TweenPlaying
                        repeat
                            local TetherPartner = LocalPlayer:GetAttribute("TetherPartner")
                            local Judgement = PlayerCharacter:GetAttribute("Judgment")
                            if Judgement and tonumber(Judgement) >= MaxJudgementThreshold and TetherPartner then
                                local Partner = Workspace:WaitForChild("Characters", math.huge):FindFirstChild(TetherPartner)
                                if Partner then
                                    local PartnerHealth = Partner:WaitForChild("HealthProperties", math.huge):WaitForChild("Health", math.huge)
                                    if PartnerHealth and PartnerHealth.Value > 0 then
                                        local PartnerCollider = Partner:WaitForChild("Collider", math.huge)
                                        TempStop = true
                                        if TweenPlaying then
                                            TweenPlaying:Cancel()
                                        end
                                        repeat
                                            if SV.Autofarm then
                                                PlayerRoot.CFrame = CFrame.new(PartnerCollider.Position + Vector3.new(0, 2, 0))
                                                TeleportStandPart()
                                            end
                                            task.wait()
                                        until (KillSwitch or not string.find(tostring(ObjectiveMessage.Value), "together") or not Partner.Parent)
                                        TempStop = false
                                    end
                                end
                            else
                                if SV.Autofarm then
                                    local EndPos = { CFrame = CFrame.new(ObbyEnd.X, ObbyEnd.Y+6, ObbyEnd.Z)}
                                    local Distance = (PlayerRoot.Position - ObbyEnd).Magnitude / 100
                                    local tweenInfo = TweenInfo.new(Distance, Enum.EasingStyle.Linear)
                                    local tween = TweenService:Create(PlayerRoot, tweenInfo, EndPos)
                                    PlayerRoot.Velocity = Vector3.new()
                                    TeleportStandPart()
                                    TweenPlaying = tween:Play()
                                end
                            end
                            task.wait()
                        until (KillSwitch or not string.find(tostring(ObjectiveMessage.Value), "together"))
                        DisconnectVariable("ConnectObjectiveMessage")
                    end)
                end)
            
                task.spawn(function()
                    local HeavenGuardianGold = Mobs:WaitForChild("HeavenGuardianGold", math.huge)
                    local GoldHealthProperties = HeavenGuardianGold:WaitForChild("HealthProperties", math.huge)
                    local GoldMaxHealth = GoldHealthProperties:WaitForChild("MaxHealth", math.huge).Value
                    local GoldPercentage = 100
                
                    local HeavenGuardianBlue = Mobs:WaitForChild("HeavenGuardianBlue", math.huge)
                    local BlueHealthProperties = HeavenGuardianBlue:WaitForChild("HealthProperties", math.huge)
                    local BlueMaxHealth = BlueHealthProperties:WaitForChild("MaxHealth", math.huge).Value
                    local BluePercentage = 100
                
                    ConnectionTable["GoldGuardian"] = GoldHealthProperties:WaitForChild("Health", math.huge).Changed:Connect(function(CurrentHealth)
                        local CurrentPercentage = GetPercentage(GoldMaxHealth, CurrentHealth)
                        if CurrentPercentage then
                            if SV.Autofarm then
                                if (CurrentPercentage + 3) <= BluePercentage then
                                    GoldPercentage = CurrentPercentage
                                    local BlueIndex = ISV.MobTable[HeavenGuardianBlue]
                                    local GoldIndex = ISV.MobTable[HeavenGuardianGold]
                                    if BlueIndex and GoldIndex then
                                        GoldIndex.Priority = nil
                                        BlueIndex.Priority = true
                                    end
                                end
                            end
                            if CurrentPercentage == 0 then
                                DisconnectVariable("GoldGuardian")
                            end
                        end
                    end)
                
                    ConnectionTable["BlueGuardian"] = BlueHealthProperties:WaitForChild("Health", math.huge).Changed:Connect(function(CurrentHealth)
                        local CurrentPercentage = GetPercentage(BlueMaxHealth, CurrentHealth)
                        if CurrentPercentage then
                            if SV.Autofarm then
                                if (CurrentPercentage + 3) <= GoldPercentage then
                                    BluePercentage = CurrentPercentage
                                    local BlueIndex = ISV.MobTable[HeavenGuardianBlue]
                                    local GoldIndex = ISV.MobTable[HeavenGuardianGold]
                                    if BlueIndex and GoldIndex then
                                        BlueIndex.Priority = nil
                                        GoldIndex.Priority = true
                                    end
                                end
                            end
                            if CurrentPercentage == 0 then
                                DisconnectVariable("BlueGuardian")
                            end
                        end
                    end)
                    if not SV.IsRanged then
                        repeat
                            MobRotationSpeed = 25.5
                            task.wait(0.1)
                        until not (HeavenGuardianGold.Parent and HeavenGuardianBlue.Parent) or KillSwitch
                        MobRotationSpeed = Options.MobRotationSpeedSliderNew.Value or 20
                    end
                end)
                
                task.spawn(function()
                    local BossRoomTrigger = MissionObjects:WaitForChild("BossRoom", math.huge):WaitForChild("BossDoorTrigger", math.huge)
                    local TouchTransmitter = BossRoomTrigger:WaitForChild("TouchInterest", math.huge)
                    BossRoomTrigger = BossRoomTrigger.Position
                    TempStop = true
                    repeat
                        if SV.Autofarm then
                            local EndPos = { CFrame = CFrame.new(BossRoomTrigger.X, BossRoomTrigger.Y, BossRoomTrigger.Z)}
                            local Distance = (PlayerRoot.Position - BossRoomTrigger).Magnitude / 100
                            local tweenInfo = TweenInfo.new(Distance, Enum.EasingStyle.Linear)
                            local tween = TweenService:Create(PlayerRoot, tweenInfo, EndPos)
                            PlayerRoot.Velocity = Vector3.new()
                            TeleportStandPart()
                            tween:Play()
                        end
                        task.wait()
                    until not TouchTransmitter.Parent or KillSwitch
                    TempStop = false
                end)
                
                task.spawn(function()
                    if SV.CanRequire and EF.Hook and EF.NewClosure then
                        local Success, Result = pcall(function()
                            SV.HeavenDisplayHook = require(Client.Gui):Get("LootReceived")._DisplayItem
                            CreateHookOnFunction(SV.HeavenDisplayHook, true)
                        end)
                        if not Success then
                            print("JDRS: executor can't disable loot screen")
                        end
                    end
                    local SpawnChest = Remotes:WaitForChild("Chests_SpawnChest", math.huge)
                    local OpenChest = Remotes:WaitForChild("Chests_OpenChest", math.huge)
                    ConnectionTable["ConnectChests"] = SpawnChest.OnClientEvent:Connect(function(a, b, GUID, d, e)
                        OpenChest:FireServer(GUID)
                        CreateHookOnFunction(SV.HeavenDisplayHook, false)
                    end)
                end)

                local BOSSSeraphiel = Mobs:WaitForChild("BOSSSeraphiel", math.huge)
                if BOSSSeraphiel then
                    local ArenaCenter = MissionObjects:WaitForChild("BossRoom", math.huge):WaitForChild("ArenaCenter", math.huge)
                    local RotationAroundCenter = math.random(0, 360)
                    local ArenaRotationSpeed = 30
                    task.spawn(function()
                        repeat
                            local DistanceFromCenter = 75 + (ArenaCenter.Size.X/2)
                            RotationAroundCenter = RotationAroundCenter + (ArenaRotationSpeed / DistanceFromCenter)
                            if not CurrentMob and SV.Autofarm then
                                PlayerRoot.CFrame = CFrame.new(ArenaCenter.Position) * CFrame.Angles(0, math.rad(RotationAroundCenter), 0) * CFrame.new(DistanceFromCenter, 25, 0)
                                PlayerRoot.CFrame = CFrame.new(PlayerRoot.Position, Vector3.new(ArenaCenter.Position.X, PlayerRoot.Position.Y, ArenaCenter.Position.Z))
                                TeleportStandPart()
                            end
                            task.wait()
                        until KillSwitch
                    end)
                    task.spawn(function()
                        repeat
                            local BossRef = Mobs:WaitForChild("BOSSSeraphiel", math.huge)
                            local function GetBossAttack()
                                return Mobs:WaitForChild("BOSSSeraphiel", math.huge):WaitForChild("MobProperties", math.huge):WaitForChild("CurrentAttack", math.huge)
                            end
                            ConnectionTable["HEAVENRAIDBOSS"] = GetBossAttack().Changed:Connect(function(CurrentAttack)
                                if CurrentAttack and SV.Autofarm then
                                    if CurrentAttack == "JudgmentWalls" then
                                        DodgeCurrentAttack(1.5, 11.5, "judgment walls")
                                    elseif CurrentAttack == "BurdenOfLight" then
                                        local CharacterCheck = Workspace:WaitForChild("Characters", math.huge):GetChildren()
                                        if #CharacterCheck > 1 then
                                            CanTarget = false
                                            TeleportMob = nil
                                            task.wait(5)
                                            CanTarget = true
                                        end
                                    end
                                end
                            end)
                            repeat
                                task.wait(0.5)
                            until not BossRef.Parent or KillSwitch
                            DisconnectVariable("HEAVENRAIDBOSS")
                            GetBossAttack = nil
                        until KillSwitch
                    end)
                end
            end
            if ISV.MissionId == 22 then
                ConnectionTable["CuringWell"] = Remotes:WaitForChild("Mob_FallenKingMinion_OnCureFountain").OnClientEvent:Connect(function()
                    local Status = PlayerCharacter:WaitForChild("Status", math.huge)
                    local DeathMark = Status:WaitForChild("DeathMark", math.huge)
                    local Fountain = Workspace:WaitForChild("CureFountainFallenKing", math.huge)
                    local FountainTeleport = Fountain:WaitForChild("ArcanePanel", math.huge)
                    TempStop = true
                    repeat
                        TeleportStandPart()
                        PlayerRoot:PivotTo(CFrame.new(FountainTeleport.Position))
                        task.wait()
                    until not DeathMark.Parent
                    Fountain:Destroy()
                    Fountain = nil
                    TempStop = false
                end)
                ConnectionTable["FALLEN_KING_ATTACKS"] = Mobs:WaitForChild("BOSSFallenKing", math.huge):WaitForChild("MobProperties", math.huge):WaitForChild("CurrentAttack", math.huge).Changed:Connect(function(CurrentAttack)
                    if not SV.Autofarm or (SV.IsRanged and not SV.SafeKillaura) then
                        return
                    end
                    if CurrentAttack == "DarkOrbAttack" then
                        DodgeCurrentAttack(6, 1, "dark orb")
                    elseif CurrentAttack == "FistSlam" then
                        DodgeCurrentAttack(0, 1, "stomp")
                    end
                end)
                repeat
                    local FallenPrince = Mobs:WaitForChild("BOSSFallenPrince", math.huge):WaitForChild("MobProperties", math.huge):WaitForChild("CurrentAttack", math.huge)
                    ConnectionTable["FALLEN_PRINCE"] = FallenPrince.Changed:Connect(function(CurrentAttack)
                        if not SV.Autofarm or (SV.IsRanged and not SV.SafeKillaura) then
                            return
                        end
                        if CurrentAttack == "Spikes" then
                            DodgeCurrentAttack(3, 1, "spikes")
                        elseif CurrentAttack == "Swing1" then
                            DodgeCurrentAttack(0.25, 1, "slash")
                        end
                    end)
                    repeat task.wait() until not FallenPrince.Parent or KillSwitch
                    DisconnectVariable("FALLEN_PRINCE")
                    FallenPrince = nil
                    task.wait()
                until KillSwitch
            end
        end)
    end)
end

SetGlobal("removing mission remotes")
do
    if IsDungeon then
        local BadRemotes = {
            ["FireDart"] = true,
            ["HammerHit"] = true,
            ["CreateBolder"] = true,
            ["ToxinTrigger"] = true,
            ["RollingBoulder"] = true
        }
        local MissionScript = ReplicatedStorage:WaitForChild("MissionScripts", math.huge):FindFirstChildWhichIsA("ModuleScript")
        if MissionScript then
            for Index, Remote in MissionScript:GetChildren() do
                if Remote and Remote.Parent then
                    if BadRemotes[Remote.Name] then
                        Remote:Destroy()
                        Remote = nil
                    end
                end
            end
        end
        MissionObjects = Workspace:WaitForChild("MissionObjects", math.huge)
        ISV.MissionId = WaitForAttribute(Workspace, "MissionId")
    end
end

SetGlobal("looking for teleport parts")
if IsDungeon then
    local Success, Result = pcall(function()
        local FindDungeonParts = {
            ["49"] = { -- tutorial
                { "CutsceneTrigger" }, { "MinibossTrigger" }, { "Cabbages", "1", "Main" }, { "Cabbages", "2", "Main" }, { "CaveTrigger" }, { "ChadCaveTrigger" }
            },
            ["54"] = { -- chad tutorial
                { "Markers", "ChadIntroTrigger" }, { "Markers", "Area2StartTrigger" }, { "Markers", "Area2_Blockage" }, { "Markers", "Area3StartTrigger" }, { "BossTrigger" }
            },
            ["47"] = { -- returning player dungeon
                { "BossTrigger" }
            },
            ["1"] = { -- Crabby crusade
                { "CutsceneTrigger" }, { "Cabbages", "1", "Main" }, { "Cabbages", "2", "Main" }, { "CaveTrigger" }
            },
            ["3"] = {}, -- Scarecrown defense 
            ["2"] = { -- Dire problem
                { "TownTalkPart" }, { "BridgeTrigger" }, { "CaveTrigger" }, { "BoulderTrigger" }, { "BoulderStopTrigger" }, { "BossIntroTrigger" }
            },
            ["4"] = { -- Kingslayer
                { "CannonTrigger" }, { "CastleTrigger" },
                NoParent = {
                    { "Cage2Marker", "Collider" }, { "Cage1Marker", "Collider" }
                }
            },
            ["6"] = {}, -- Gravetower dungeon
            ["11"] = { -- Temple of ruin
                { "Room1Trigger" }, { "Room2Trigger" }, { "Room3Trigger" }, { "Room4Trigger" }, { "WallsTrigger" }, { "WallsFinalTrigger" },
                NoParent = {
                    { "TreasureMarker", "Collider" }
                }
            },
            ["12"] = { -- Mama trauma
                { "PreBridgeTrigger" }, { "BridgeTrigger" }, { "CaveSpawnTrigger" }, { "CliffsideEndTrigger"},
                DeleteParts = {
                    { "CheckpointTriggers" }, { "MissionObjects", "TempleTrigger" }
                }
            },
            ["13"] = { -- Volcanos shadow
                { "VineRoomTrigger" }, { "CheckpointTrigger" }, { "CannonTrigger" }, { "ObbyTrigger" }, { "BossTrigger" },
                DeleteParts = {
                    { "MissionObjects", "LavaTriggers" }, { "MissionObjects", "LavaTrigger" }
                }
            },
            ["7"] = {}, -- Volcano dungeon
            ["14"] = { -- Mountain pass
                { "CaveTrigger" }, { "DropTrigger" }
            },
            ["15"] = { -- Winter cavern
                { "BossTrigger" }
            },
            ["16"] = { -- Winter dungeon
                { "CastleGateTrigger" }, { "BossTrigger" }
            },
            ["20"] = { -- Scrap canyon
                { "SceneTrigger" }
            },
            ["19"] = {}, -- Deserted burrowmine
            ["18"] = { -- Pyramid dungeon
                { "OutsideBossTrigger" }, { "BossTrigger" },
                DeleteParts = {
                    { "MissionObjects", "WaterKillPart" }, { "MissionObjects", "BossKillPart" }
                }
            },
            ["24"] = {}, -- Konoh heartlands
            ["35"] = {}, -- Konoh inferno
            ["21"] = { -- Prison tower
                { "WaveStarter", Regenerates = true }, { "WaveExit"}, { "BossDoorTrigger" }
            },
            ["25"] = { -- Rough waters
                { "Area1Trigger" }, 
                CheckpointGates = {
                    { "Checkpoint4", "VentButton", "FinishRing" }
                }
            },
            ['36'] = { -- Treasure hunt
                CheckpointGates = {
                    { "Checkpoint1", "FinishRing" }, { "Checkpoint3", "TriggerObjective" }, { "Checkpoint3", "ObbyTrigger" }, { "Checkpoint7", "ObbyTrigger" }
                },
                { "StartWaveDefense" },
                DeleteParts = {
                    { "MissionObjects", "DamageCeiling" }
                }
            },
            ["23"] = { -- Atlantis tower
                { "WaveStarter", Regenerates = true }, { "WaveExit"}, { "BossDoorTrigger" }
            },
            ["26"] = { -- The underworld
                { "Trigger1" }, { "Trigger2" }, { "Trigger3" }
            },
            ["37"] = { -- The labyrinth
                CheckpointGates = {
                    { "Checkpoint5", "ObbyTrigger" }
                },
                { "BossCutsceneTrigger" }
            },
            ["27"] = { -- Mexuvian tower
                { "WaveStarter", Regenerates = true }, { "WaveExit"}, { "BossDoorTrigger" }
            },
            ["30"] = { --Rescue in the ruin
                { "FloorTrigger" }, { "Trigger1" }, { "BottomElevatorTrigger" }, { "MiddleElevatorTrigger" }, { "TopElevatorTrigger" }
            },
            ["31"] = {}, -- Ruin rush
            ["29"] = { -- Oasis tower
                { "WaveStarter", Regenerates = true }, { "WaveExit"}, { "BossDoorTrigger" }
            },
            ["32"] = { -- Treetop trouble
                { "ObbyTrigger5" }
            },
            ["33"] = {
                CheckpointGates = { -- Aether fortress
                    { "Checkpoint3", "ObbyTrigger" }, { "Checkpoint7", "ObbyTrigger" }
                }
            },
            ["34"] = { -- Aether tower
                { "WaveStarter", Regenerates = true }, { "WaveExit"}, { "BossDoorTrigger" }
            },
            ["41"] = { -- Crystal chaos
                CheckpointGates = {
                    { "Checkpoint3", "ObbyTrigger" }, { "Checkpoint5", "EnterArena" }, { "Checkpoint6", "ObbyTrigger" }
                },
                { "BossTrigger" }
            },
            ["42"] = { -- Crystal academy
                CheckpointGates = {
                    { "Checkpoint3", "ObbyTrigger" }, { "Checkpoint6", "ObbyTrigger" }
                },
                { "BossTrigger" }
            },
            ["43"] = { -- Arcane tower
                { "WaveStarter", Regenerates = true }, { "WaveExit"}, { "BossDoorTrigger" }
            },
            ["39"] = { -- Celestial tower
                NoParent = {
                    { "LobbyTeleport", "Interaction" }, { "Boss_Gate", "Interactions", "Bounds" }
                }
            },
            ["38"] = { -- Infinite tower
                NoParent = {
                    { "LobbyTeleport", "Interaction" }, { "Boss_Gate", "Interactions", "Bounds" }
                }
            },
            ["53"] = {}, -- heavenly raid
            ["45"] = {}, -- kraken raid
            ["56"] = {
                { "BackTeleporter" }, { "Teleporter", AutoTouch = true }, { "BossDoorTrigger" }, { "MinibossExit" }
            },
            ["22"] = {} -- fallen throne
        }

        local CurrentDungeon = FindDungeonParts[tostring(ISV.CurrentDungeonID)]
        if not CurrentDungeon then
            SaveErrorToFile("DUNGEON UNSUPPORTED", "an update to the script is required for this dungeon to work", "if this is a new dungeon please wait until I can update the script")
            return
        end

        for Index, Parts in CurrentDungeon do
            if type(Index) == "number" then
                table.insert(SV.DungeonPartList, Parts)
            else
                SV.DungeonPartList[Index] = {}
                for _, Part in Parts do
                    table.insert(SV.DungeonPartList[Index], Part)
                    task.wait()
                end
            end
            task.wait()
        end

        FindDungeonParts = nil

        for Index, Parts in SV.DungeonPartList do
            if type(Index) == "number" then
                task.spawn(function()
                    FindPart(nil, Parts)
                end)
            else
                for TableRef, Part in Parts do
                    task.spawn(function()
                        FindPart(tostring(Index), Part)
                    end)
                    task.wait()
                end
            end
            task.wait()
        end
        SV.DungeonPartList = nil
        if IsTower then
            task.spawn(function()
                if ISV.MissionId ~= 56 then
                    local WaveExitPart = nil
                    ConnectionTable["ConnectTower"] = Remotes:WaitForChild("Towers_UpdateChests", math.huge).OnClientEvent:Connect(function(RandomTable, KilledMobs, TotalMobs, Progress, RandomBoolean)
                        if WaveExitPart then
                            if KilledMobs == TotalMobs then
                                TeleportParts[WaveExitPart].DontTeleport = nil
                            else
                                TeleportParts[WaveExitPart].DontTeleport = true
                            end
                        end
                    end)
                    ConnectionTable["ConnectTowerPrint"] = Remotes:WaitForChild("Towers_Print").OnClientEvent:Connect(function(Text)
                        if WaveExitPart then
                            if string.find(Text, "false") then
                                DisconnectVariable("ConnectTower")
                                TeleportParts[WaveExitPart].DontTeleport = true
                                DisconnectVariable("ConnectTowerPrint")
                            end
                        end
                    end)
                    WaveExitPart = MissionObjects:WaitForChild("WaveExit", math.huge)
                end
            end)
        end
    end)
    if not Success then
        SaveErrorToFile("FIND TELEPORT PARTS", Result)
    end
end

--SetGlobal("waiting for character")
--if not IsMainMenu then
--    local IsDead = false
--    local AlreadyCheckingLives = false
--    repeat
--        if IsDungeon then
--            task.spawn(function()
--                if AlreadyCheckingLives then
--                    return
--                end
--                AlreadyCheckingLives = true
--                if GetLives() == 0 then
--                    IsDead = true
--                    LoadingStep(true)
--                    RejoinLastDungeon(false)
--                    RestartDungeon(true)
--                    return
--                end
--                AlreadyCheckingLives = false
--            end)
--        elseif IsWorld then
--            RejoinLastDungeon(false)
--        end
--        task.wait(0.2)
--    until LocalPlayer.Character
--    if IsDead then
--        return
--    end
--    PlayerCharacter = LocalPlayer.Character
--    PlayerCollider = PlayerCharacter:WaitForChild("Collider")
--    PlayerRoot = PlayerCharacter:WaitForChild("HumanoidRootPart")
--    print("JDRS: local player character found")
--end

SetGlobal("prevent falling part")
if IsDungeon then
    task.spawn(function()
        CheckForCharacter()
        PlayerStandPart = Instance.new("Part")
        PlayerStandPart.Size = Vector3.new(3, 1, 3)
        PlayerStandPart.Parent = Workspace
        PlayerStandPart.Anchored = true
        PlayerStandPart.Transparency = 1
        PlayerStandPart.CanCollide = true
        PlayerStandPart.CanTouch = false
        PlayerStandPart.CanQuery = false
        StandPartHeight = GetPlayerSize() + PlayerStandPart.Size.Y/2.75
    end)
end

SetGlobal("spawning function")
if not IsMainMenu then
    SpawnFunctions = {
        CheckForAvoidMobs, MobScanner, CheckPlayerPing,
        ConnectMissionFinished, ConnectTowerFinished,
    }
    for _, SpawnFunction in SpawnFunctions do
        task.spawn(function()
            SpawnFunction()
        end)
    end
end

SetGlobal("getting class variables")
if not IsMainMenu then
    ISV.PlayerClass = WaitForAttribute(LocalPlayer, "Class")
    ISV.PlayerLevel = WaitForAttribute(LocalPlayer, "Level")
    ISV.PlayerPrestige = WaitForAttribute(LocalPlayer, "Prestige")
    PlayerProfile = ReturnChild(PlayerGui, "Profile")
    ProfileInventory = ReturnChild(PlayerProfile, "Inventory")
    SV.Parties = ReturnChild(ReplicatedStorage, "Parties")
end

SetGlobal("equipment pop up screen")
if IsTower and SV.CanRequire and EF.Hook and EF.NewClosure then
    local Success, Result = pcall(function()
        local DisplayItem = require(Client.Gui):Get("LootReceived")._DisplayItem
        CreateHookOnFunction(DisplayItem, true)
    end)
    if not Success then
        print("JDRS: executor can't disable loot screen")
    end
end

SetGlobal("connecting drops/chests")
do
    local CoinEvent = Remotes:WaitForChild("Drops_CoinEvent", math.huge)
    ConnectionTable["CollectDrops"] = CoinEvent.OnClientEvent:Connect(function(DropData)
        if SV.CollectDrops then
            CoinEvent:FireServer(DropData.id)
        else
            SV.Drops[DropData.id] = time()
        end
    end)
    local SpawnChest = Remotes:WaitForChild("Chests_SpawnChest", math.huge)
    local OpenChest = Remotes:WaitForChild("Chests_OpenChest", math.huge)
    ConnectionTable["ConnectChests"] = SpawnChest.OnClientEvent:Connect(function(ChestName, Location, GUID, d, e)
        if SV.CollectChests then
            OpenChest:FireServer(GUID)
        else
            table.insert(SV.Chests, GUID)
        end
    end)
end

SetGlobal("clean up script")
function CleanUpScript()
    for Index in Toggles do
        Toggles[tostring(Index)]:SetValue(false) -- safely turn off all toggles
    end
    for Index in Options do
        local StringIndex = tostring(Index)
        if string.find(StringIndex, "Dropdown") and not string.find(StringIndex, "UnloadTabDropdown") then
            Options[StringIndex]:SetValue({}) -- safely erase all dropdowns to turn attached functions off
        end
    end
    ISV.TeleportingToAnotherServer = true
    if not IsMainMenu and SV.CanRequire and EF.Hook and EF.CheckHook and EF.ClearHook and EF.NewClosure then
        local rPlayerRemover = require(SMobs:WaitForChild("PlayerRemover", math.huge))
        CreateHookOnFunction(rPlayerRemover.AddMobToSearch, false)
        for Index, Mob in Mobs:GetChildren() do
            rPlayerRemover:AddMobToSearch(Mob)
        end
        if SV.IsRanged then
            for Mob, MobData in ISV.MobTable do
                local MobCollider = Mob:WaitForChild("Collider", 5)
                if MobCollider then
                    MobCollider.Size = MobCollider.Size*2
                end
            end
        end
        rPlayerRemover = nil
        local rDrops = require(Drops)
        CreateHookOnFunction(rDrops.DropStarterpassExp, false)
        CreateHookOnFunction(rDrops.DropBattlepassExp, false)
        CreateHookOnFunction(rDrops.DropHealthOrb, false)
        CreateHookOnFunction(rDrops.SpawnCoinsLocal, false)
        rDrops = nil
        local rModelProvider = require(ModelProvider)
        CreateHookOnFunction(rModelProvider.GetModel, false)
        rModelProvider = nil
        local rEffects = require(Effects)
        CreateHookOnFunction(rEffects.RenderDamageNumber, false)
        CreateHookOnFunction(rEffects.MakeProjectile, false)
        CreateHookOnFunction(rEffects.DoEffect, false)
        CreateHookOnFunction(rEffects.PlayAt, false)
        CreateHookOnFunction(rEffects.EmitAt, false)
        rEffects = nil
        local rGui = require(Client.Gui)
        CreateHookOnFunction(rGui:Get("LootReceived")._DisplayItem, false)
        rGui = nil
        local rActions = require(Client.Actions)
        rActions:SetSkillDisabled("Primary", false)
        rActions:SetSkillDisabled("Skill1", false)
        rActions:SetSkillDisabled("Skill2", false)
        rActions:SetSkillDisabled("Skill3", false)
        rActions:SetSkillDisabled("Ultimate", false)
        CreateHookOnFunction(rActions.IsBusy, false)
        CreateHookOnFunction(rActions.Knockdown, false)
        rActions = nil
    end
    if DC then
        if EF.Queue then
            local FileName = "JDRS/AutoExecute"
            if isfile(FileName) then
                delfile(FileName)
                EF.ClearQueue()
            end
        end
        if IsDungeon then
            if SV.PlayerCamera and SV.PlayerCamera.Parent and PlayerRoot == SV.PlayerCamera.Parent then
                Workspace.CurrentCamera.CameraSubject = SV.PlayerCamera
            else
                Workspace.CurrentCamera.CameraSubject = PlayerRoot:WaitForChild("Part", math.huge)
            end
        end
        if SV.WalkspeedManager then
            if ISV.IsMobile then
                SV.WalkspeedManager:SetBaseSpeed(28)
            else
                SV.WalkspeedManager:SetBaseSpeed(20)
            end
        end
        if ISV.RenderingScreen then
            ISV.RenderingScreen:Destroy()
            ISV.RenderingScreen = nil
            RunService:Set3dRenderingEnabled(true)
        end
        for Key in ISV do
            ISV[Key] = nil
        end
        for Key in EF do
            EF[Key] = nil
        end
        ISV = nil
        if PlayerRoot then
            PlayerRoot.CanCollide = true
        end
        for Part, PartData in TeleportParts do
            if Part and Part.Parent then
                Part.Size = PartData.OriginalSize
                Part.CanCollide = PartData.OriginalCollision
                Part.Position = PartData.OriginalLocation
            end
        end
        ScriptUnloaded, Remotes, SetGlobal,
        RequestMessage = nil
    end
    for Key in SV do
        SV[Key] = nil
    end
    for Index, Connection in ConnectionTable do
        Connection:Disconnect()
        ConnectionTable[Index] = nil
    end
    _G.Is_Script_Running = nil
    Library:Unload()
    SaveErrorToFile = function()
        return
    end
    if PlayerStandPart then
        PlayerStandPart:Destroy()
    end
    Library, SaveManager, MakeGuiElement, MakeErrorGui, ReturnService,
    GetShared, ReturnChild, WaitForAttribute, Workspace, Players,
    CoreGui, StarterGui, ReplicatedStorage, HttpService, VirtualUser,
    RunService, MarketplaceService, TeleportService, Shared, Battlepass,
    Charms, Chests, Drops, Effects, Health,
    Inventory, Items, Missions, SMobs, ModelProvider,
    Party, Pets, Quests, Shop, Skills,
    Teleport, Camera, Mobs, MissionObjects, LocalPlayer,
    PlayerName, PlayerID, PlayerGui, PlayerPing, PlayerProfile,
    ProfileInventory, PlayerCharacter, PlayerCollider, PlayerRoot, AddedDelay,
    Xdistance, Ydistance, TempStop, HoldForRealTime, RestartAtFloor,
    CurrentMob, IsMobCamera, KeepTier, SellItemCheck, OffsetMax,
    EquipInProgress, MobRotationSpeed, DelayPetAttacks, IsAliveMobs, DiscordPingType,
    TeleportMob, StuckDelay, DelayAttacks, IsBoss, EventOverride,
    CanTarget, PingMultiplie, StringPlaceID, IsWorld, IsMainMenu,
    IsDungeon, IsTower, SaveScriptToFiles, AvoidMobs, TeleportParts,
    FormatNumber, FormatDecimal, GetPercentage, SecondsToString, IsMissionOver,
    CheckForAvoidMobs, CheckPlayerPing, MobScanner, PingOnceUnlocked, PingForCap,
    GetDifficulty, GetLives, PartyLeaderCheck, ReplayDungeonLoop, RejoinLastDungeon,
    RestartDungeon, CollectChests, ClaimAllQuests, GetDungeonImage, ConnectMissionFinished,
    ConnectTowerFinished, GetRarity, EquipNewItemAdded, StatTotals, CollectTowerChests,
    CollectCoins, GetGuild, IsTowerEgg, SellItem, BuyFromLocalShop,
    BuyFromEggShop, OpenMenu, UpgradeToMax, ExpandPartSize, FindPart,
    ToggleMenu, DodgeCurrentAttack, TeleportToOrb, BuildAttackData, GetPlayerPet,
    GetPlayerClass, BuildShopValues, DisconnectVariable, TeleportStandPart, GetPlayerSize,
    PlayerStandPart, StandPartHeight, CreateHookOnFunction, Class, ClassSkills,
    PetSkills, ItemSellCheck, RecycleFromInventory = nil
end

SetGlobal("obsidian save manager")
SaveManager = SaveScriptToFiles("https://raw.githubusercontent.com/deividcomsono/Obsidian/main/addons/SaveManager.lua", "S", 1)

print("Script took", FormatDecimal(os.clock() - ScriptLoadingStart), "seconds to fully load from execution time")
ScriptLoadingStart = nil

SetGlobal("loading configs")
SaveManager:SetLibrary(Library)
SaveManager:IgnoreThemeSettings()
SaveManager:SetIgnoreIndexes({ "MenuKeybind" })
SaveManager:SetFolder("JDRS/saved_configs")
SaveManager:BuildConfigSection(ConfigTab)
SaveManager:LoadAutoloadConfig()

do
    SetGlobal("checking platform")
    local GetPlatform = game:GetService("UserInputService"):GetPlatform()
    if GetPlatform ~= Enum.Platform.Android and GetPlatform ~= Enum.Platform.IOS then
        Library:Notify("You can press 0 (zero key) to open/close the menu", 10)
    else
        ISV.IsMobile = true
    end
end

SetGlobal("checking for old obsidian")
if not ISV.IsMobile and EF.HideGui and not SV.BadExecutor then
    local MainUI = EF.HideGui():WaitForChild("Obsidian", math.huge):WaitForChild("Main", math.huge)
    ConnectionTable["obsidianguihandler"] = UserInputService.InputBegan:Connect(function(Key)
        if Key.KeyCode == Enum.KeyCode.Zero then
            if MainUI.Visible then
                MainUI.Visible = false
            else
                MainUI.Visible = true
            end
        end
    end)
end

SetGlobal("toggle menu")
if Toggles.HideGuiToggle.Value then
    Library:Toggle()
end

SetGlobal("leaderboard info set up")
if IsWorld or IsDungeon then
    task.spawn(function()
        local Success, Result = pcall(function()
            local GetScore = Remotes:WaitForChild("LeaderboardHookup_GetScore", math.huge)
            if not SV.DungeonsTab then
                if GetLeaderboardScore("C_NP1", SV.TotalNightmareLabel, SV.DailyNightmareLabel, SV.StopAfterTotalNightmare, SV.StopAfterDailyNightmare) then
                    Library:Notify("Nightmare portal clear limit reached.", 999999999)
                    local TempStop = true
                    local CanTarget = false
                    if SV.NightmarePing then
                        PingForCap("Nightmare portal")
                    end
                end
            end -- for unloaded dungeons tan
            if not SV.GuildTab then
                local TotalPointData = GetScore:InvokeServer("G_POINTS22", 1)
                local DailyPointData = Remotes:WaitForChild("Profile_GetOwnCollectionValue", math.huge):InvokeServer("GuildPointsEarnedToday")
                local GuildPointTotal = TotalPointData[1]
                local GuildPointTotalLimit = tonumber(SV.StopAfterTotalPoints)
                local GuildPointDaily = DailyPointData
                local GuildPointDailyLimit = tonumber(SV.StopAfterDailyPoints)
                SV.TotalGuildPointLabel:SetText("Total Guild Points: " ..FormatNumber(GuildPointTotal))
                SV.DailyGuildPointLabel:SetText("Daily Guild Points: " ..FormatNumber(GuildPointDaily))
                if (GuildPointTotalLimit and (GuildPointTotal >= GuildPointTotalLimit)) or (GuildPointDailyLimit and (GuildPointDaily >= GuildPointDailyLimit)) then
                    Library:Notify("Guild point limit reached.", 999999999)
                    CanTarget = false
                    TempStop = true
                    if SV.GuildPing then
                        PingForCap("Guild Point")
                    end
                end
            end -- for unloaded guild tab
        end)
        if not Success then
            print(Result)
        end
    end)
end

if GetLives() == 0 then
    RestartDungeon()
end

SetGlobal("end")
