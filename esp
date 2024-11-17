-- LocalScript inside the TextButton

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()  -- Ensure character is loaded
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")  -- The part to follow (HumanoidRootPart)
local screenGui = player.PlayerGui:WaitForChild("ScreenGui")  -- The ScreenGui
local button = script.Parent  -- The button that triggers the action

local followingPart = nil  -- Variable to hold the part that will follow the player

-- Function to create a part and make it follow the player
local function createFollowingPart()
	-- Create the part in the workspace
	followingPart = Instance.new("Part")
	followingPart.Shape = Enum.PartType.Ball  -- You can change this to Block, Sphere, etc.
	followingPart.Size = Vector3.new(2, 2, 2)  -- Adjust the size of the part
	followingPart.Anchored = false  -- Make it follow the player (don't anchor it)
	followingPart.CanCollide = false  -- Prevent collision with other parts
	followingPart.Material = Enum.Material.Neon  -- Neon material for visibility
	followingPart.BrickColor = BrickColor.new("Bright red")  -- Bright color for visibility
	followingPart.Parent = workspace  -- Add to the workspace

	-- Create a loop to continuously follow the player's HumanoidRootPart
	game:GetService("RunService").Heartbeat:Connect(function()
		if followingPart then
			followingPart.Position = humanoidRootPart.Position + Vector3.new(0, 5, 0)  -- Position above the player
		end
	end)
end

-- Function to handle the button click
local function onButtonClick()
	createFollowingPart()  -- Call the function to create and follow the part
end

-- Connect the button click to the function
button.MouseButton1Click:Connect(onButtonClick)
