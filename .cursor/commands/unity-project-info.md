# Unity Project Info

Display comprehensive project information including tags, layers, Unity version, and project settings.

## Tools Used

- `project_info` resource - Get Unity project details
- `project_tags` resource - Get available tags
- `project_layers` resource - Get available layers
- `unity_instances` resource - Get Unity instance information (optional)

## Workflow

1. Use `project_info` resource to get:
   - Unity version
   - Project name
   - Project path
   - Other project metadata

2. Use `project_tags` resource to get:
   - List of all available tags in the project

3. Use `project_layers` resource to get:
   - List of all available layers in the project

4. Optionally use `unity_instances` resource to show:
   - Active Unity Editor instances

5. Display a comprehensive summary including:
   - Project name and Unity version
   - Available tags (list)
   - Available layers (list)
   - Any other relevant project information

## Example Output

```
Unity Project Information:
- Project: MyGame
- Unity Version: 2022.3.15f1
- Available Tags: Untagged, Respawn, Finish, EditorOnly, MainCamera, Player, GameController
- Available Layers: Default, TransparentFX, Ignore Raycast, Water, UI
```