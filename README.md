# Module3D
Module3D is a helper module for adorning 3D objects to 2D frames
in ScreenGuis, BillboardGuis, or SurfaceGuis. This version uses
ViewportFrames to make development easier with more features and
less overhead on the developer's part.

## Code Example
```lua
local Frame = script.Parent:WaitForChild("Frame")
local Module3D = require(game.ReplicatedStorage:WaitForChild("Module3D"))
local Towers = game.ReplicatedStorage:WaitForChild("Towers")

local Model3D = Module3D:Attach3D(Frame,Towers)
Model3D:SetDepthMultiplier(1.2)
Model3D.CurrentCamera.FieldOfView = 5
Model3D.Visible = true

game:GetService("RunService").RenderStepped:Connect(function()
    Model3D:SetCFrame(CFrame.Angles(0, tick() % (math.pi * 2), 0) * CFrame.Angles(math.rad(-10), 0, 0))
end)
```

## Roblox Model
This model can be found in the Roblox library.
https://www.roblox.com/library/2615023691/Module3D-V6

For use with Rojo, only the `Module3D.lua` file is
needed since there is no external dependencies.

## Contributing
Both issues and pull requests are accepted for this project.
More information can be found [here](docs/contributing.md).

## License
Nexus Unit Testing is available under the terms of the MIT 
Licence. See [LICENSE](LICENSE) for details.