# Setup Standard Folders

Ensure all standard Unity project folders exist in the Assets directory.

## Tools Used

- `manage_asset` tool - Create folders
- File system checking - Verify folder existence

## Workflow

1. **Check existing structure:**
   - Check which standard folders already exist
   - Read current Assets folder structure

2. **Create missing folders:**
   - Create any missing standard folders using `manage_asset`:
     - `Assets/Scenes/` - For scene files
     - `Assets/Prefabs/` - For prefab assets
     - `Assets/Scripts/` - For C# script files
     - `Assets/UI Elements/` - For UI-related assets
     - `Assets/Materials/` - For material assets (create if needed)
     - `Assets/Textures/` - For texture assets (create if needed)

3. **Project type specific folders:**
   - Ask user or check project to determine if 3D or 2D:
     - 3D Projects: `Assets/Models/` - For 3D model files
     - 2D Projects: `Assets/Sprites/` - For 2D sprite assets

4. **Verify creation:**
   - Confirm all folders were created successfully
   - List all created folders

5. **Report results:**
   - Show which folders already existed
   - Show which folders were created
   - Display the final folder structure

## Example Output

```
Standard Folders Setup:
- Scenes/ (already existed)
- Prefabs/ (created)
- Scripts/ (created)
- UI Elements/ (created)
- Materials/ (created)
- Textures/ (created)
- Models/ (created - 3D project)

All standard folders are now in place.
```

## Notes

- Standard folders should exist in every Unity project
- Use this when starting a new project or organizing an existing one
- Folders are created empty - assets will be placed in them later
- Follows Unity MCP workflow rules for folder organization
