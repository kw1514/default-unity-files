# Asset Structure

Show the organization of the Assets folder and its subfolders.

## Tools Used

- `manage_asset` tool - Read folder structure
- File system reading - List directories in Assets folder

## Workflow

1. **Read Assets folder:**
   - List all root folders in `Assets/`
   - Show the hierarchy and organization
   - Identify standard Unity folders

2. **Display structure:**
   - Show a tree view of the Assets folder
   - Highlight standard folders:
     - Scenes
     - Prefabs
     - Scripts
     - Materials
     - Textures
     - Models/Sprites (project type dependent)
     - UI Elements
   - Show any custom organizational folders

3. **Provide context:**
   - Explain the organizational pattern if clear
   - Note which standard folders exist
   - Suggest where new assets should be placed based on structure
   - Identify any missing standard folders

## Example Output

```
Assets Folder Structure:
Assets/
├── Scenes/
│   ├── MainMenu.unity
│   └── GameLevel.unity
├── Prefabs/
│   ├── Player.prefab
│   └── Enemy.prefab
├── Scripts/
│   ├── Controllers/
│   └── Managers/
├── Materials/
├── Textures/
└── UI Elements/

Organization: Standard Unity structure with feature-based Scripts subfolders
```

## Notes

- Understanding asset structure helps maintain organization
- Use this before creating assets to find the right location
- Follow existing patterns when adding new assets
- Standard folders should exist in every project
