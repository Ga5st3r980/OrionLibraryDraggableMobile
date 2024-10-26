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
# Creating a section
local Section = Tab:AddSection({
	Name = "Section"
})
# Creating a button
Tab:AddButton({
	Name = "Button!",
	Callback = function()
      		print("button pressed")
  	end    
})
# Creating a CheckBox toogle
Tab:AddToggle({
	Name = "This is a toggle!",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})
# Changing the value of an existing Toogle
CoolToggle:Set(true)
# Creating a Color Picker
Tab:AddColorpicker({
	Name = "Colorpicker",
	Default = Color3.fromRGB(255, 0, 0),
	Callback = function(Value)
		print(Value)
	end	  
})
# Setting the Color Picker's value
ColorPicker:Set(Color3.fromRGB(255,255,255))
# Creating a Slider
Tab:AddSlider({
	Name = "Slider",
	Min = 0,
	Max = 20,
	Default = 5,
	Color = Color3.fromRGB(255,255,255),
	Increment = 1,
	ValueName = "bananas",
	Callback = function(Value)
		print(Value)
	end    
})
# Change Slider value
Slider:Set(2)
# Creating a Label
Tab:AddLabel("Label")
# Changing the value of an existin Label
CoolLabel:Set("Label New!")
# Creating a Paragraph
Tab:AddParagraph("Paragraph","Paragraph Content")
# Changing an existing Paragraph
CoolParagraph:Set("Paragraph New!", "New Paragraph Content!")
# Creating an adaptive input
Tab:AddTextbox({
	Name = "Textbox",
	Default = "default box input",
	TextDisappear = true,
	Callback = function(Value)
		print(Value)
	end	  
})
# Creating a Keybind
Tab:AddBind({
	Name = "Bind",
	Default = Enum.KeyCode.E,
	Hold = false,
	Callback = function()
		print("press")
	end    
})
# Changing the value of a Bind
Bind:Set(Enum.KeyCode.E)
# Creating a Dropdown menu
Tab:AddDropdown({
	Name = "Dropdown",
	Default = "1",
	Options = {"1", "2"},
	Callback = function(Value)
		print(Value)
	end    
})
# Adding a set of new Dropdown buttons to an existing menu
Dropdown:Refresh(List<table>,true)
# Selecting a dropdown menu
Dropdown:Set("dropdown option")
# Finishing your script (optional)
OrionLib:Init()
# How flags works.
The flags feature in the ui may be confusing for some people. It serves the purpose of being the ID of an element in the config file, and makes accessing the value of an element anywhere in the code possible. Below in an example of using flags.

Tab1:AddToggle({
    Name = "Toggle",
    Default = true,
    Save = true,
    Flag = "toggle"
})

print(OrionLib.Flags["toggle"].Value) -- prints the value of the toggle.

Flags only work with the toggle, slider, dropdown, bind, and colorpicker.
# Making your interface work with configs

In order to make your interface use the configs function you first need to add the SaveConfig and ConfigFolder arguments to your window function. The explanation of these arguments in above. Then you need to add the Flag and Save values to every toggle, slider, dropdown, bind, and colorpicker you want to include in the config file. The Flag = <string> argument is the ID of an element in the config file. The Save = <bool> argument includes the element in the config file. Config files are made for every game the library is launched in.
# Destroying the interface (for a button)
OrionLib:Destroy()
