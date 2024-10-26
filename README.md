# Orion Linrary Mobile
This documentation is for the stable release of Orion Library Draggable
# Booting the library
local OrionLib = loadstring(game:HttpGet(('https://pastebin.com/raw/WRUyYTdY')))()
# Notifying the user:
OrionLib:MakeNotification({
	Name = "Title!",
	Content = "Notification content... what will it say??",
	Image = "rbxassetid://4483345998",
	Time = 5
})
# Creating a window
local Window = OrionLib:MakeWindow({Name = "Title of the library", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})
# Creating a tab
local Tab = Window:MakeTab({
	Name = "Tab 1",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
