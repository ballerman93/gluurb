repeat task.wait() until game:IsLoaded()
task.wait(0.3)
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
local Window = Rayfield:CreateWindow({
   Name = "Trick Hub",
   Icon = 0, 
   LoadingTitle = "Trick Hub",
   LoadingSubtitle = "",
   ShowText = "", 
   Theme = "Default",

   ToggleUIKeybind = "K", 

   DisableRayfieldPrompts = true,
   DisableBuildWarnings = false,

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, 
      FileName = "TrickHubDRMG"
   },

   Discord = {
      Enabled = false, 
      Invite = "noinvitelink", 
      RememberJoins = true
   },

   KeySystem = false,
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", 
      FileName = "Key",
      SaveKey = true,
      GrabKeyFromSite = false,
      Key = {"Hello"} 
   }
})

local Main = Window:CreateTab("Main", "home") 
local Server = Window:CreateTab("Server", "Computer") 
local Client = Window:CreateTab("Client", "eye") 
local ScoreExploit = Main:CreateSection("Score Exploit")
local IsScoreExploiting = false
local ScoreExploitToggle = Main:CreateToggle({
   Name = "Score Exploit",
   CurrentValue = false,
   Flag = "ScoreExploitTog", 
   Callback = function(Value)
 IsScoreExploiting = Value
        while task.wait() do
          if IsScoreExploiting and game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui.SelectedSongServ.Value == "Black Knife X" then
              

warn("no")
local args = {
	999,
	"Black Knife X",
	false,
	"Default",
	3,
	false
}
game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("UwU"):FireServer(unpack(args))
game:GetService("Players").LocalPlayer.PlayerGui.ScreenGui.SongSelect.Visible = true
end




            
        end
   end,
})
local ScoreExploit = Main:CreateLabel("Select the song Black Knife X, and run an Autoclicker on the play button. I'm way too lazy to integrate that myself", "info")
local Notice = Main:CreateLabel("Staff said that this is externally detected (You will most likely get banned for doing this)", "octagon-alert")

local IHateSettingLimits = Main:CreateSection("Custom Settings")
local ScoreExploit = Main:CreateLabel('This avoids blockages like "Note Speed Atleast 0.5"', "info")
local NoteSpeedChanger = Main:CreateSlider({
   Name = "Custom Note Speed",
   Range = {0, 5},
   Increment = 0.1,
   Suffix = "",
   CurrentValue = game:GetService("Players").LocalPlayer.Settings.NoteSpeed.Value,
   Flag = "CustomNoteSpeedSlider", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   local args = {
	tostring(Value),
	"NoteSpeed"
}
game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("KeybindChangeEvent"):FireServer(unpack(args))

   end,
})

local PlayAnimation = Server:CreateButton({
   Name = "Run Animation",
   Callback = function()
    local args = {
	true,
	game:GetService("Players").LocalPlayer.Settings.SelectedAnim.Value
}
game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("EquipToolSearver"):FireServer(unpack(args))

   end,
})
local StopAnimation = Server:CreateButton({
   Name = "Stop Animation",
   Callback = function()
    local args = {
	false,
	game:GetService("Players").LocalPlayer.Settings.SelectedAnim.Value
}
game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("EquipToolSearver"):FireServer(unpack(args))

   end,
})
local INFOANIMATION = Server:CreateLabel("This only gives you the tools for the Animation. But atleast it's not visual!", "info")
local ClientsidedStuff = Client:CreateLabel("This is all visual, only you'll see this. Put to 0 to disable", "info")
local Slider = Client:CreateSlider({
   Name = "Top 10 Winstreak ChatTag",
   Range = {0, 10},
   Increment = 1,
   Suffix = "",
   CurrentValue =  game:GetService("Players").LocalPlayer.Streak.Value,
   Flag = "ClientSidedLeaderboardWinstreak",
   Callback = function(Value)
   game:GetService("Players").LocalPlayer.Streak.Value = Value
   end,
})
local Slider = Client:CreateSlider({
   Name = "Top 10 Worldwide ChatTag",
   Range = {0, 10},
   Increment = 1,
   Suffix = "",
   CurrentValue = game:GetService("Players").LocalPlayer.scorerank.Value,
   Flag = "ClientSidedLeaderboardWinstreak",
   Callback = function(Value)
   game:GetService("Players").LocalPlayer.scorerank.Value = Value
   end,
})
