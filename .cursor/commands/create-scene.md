# Create Scene

Create a new scene file in the Unity project.

Usage: `/create-scene <scene-name>`

## Tools Used

- `manage_scene` tool - Create new scenes
- `manage_asset` tool - Ensure Scenes folder exists
- `editor_state` resource - Verify scene creation

## Workflow

1. **Check Scenes folder:**
   - Verify `Assets/Scenes/` folder exists
   - If it doesn't exist, create it using `manage_asset`
   - Read existing `Assets/Scenes/` structure to understand subfolder organization

2. **Determine scene path:**
   - Check if scene name already exists
   - Determine appropriate location (root Scenes folder or subfolder)
   - Follow existing project organization patterns
   - If unsure about placement, ask the user

3. **Create the scene:**
   - Use `manage_scene` tool to create the new scene
   - Provide the full path (e.g., `Assets/Scenes/Level1.unity`)
   - The scene will be created and loaded in Unity

4. **Verify creation:**
   - Use `editor_state` to confirm the new scene is active
   - Check that the scene file exists
   - Report success to the user

## Notes

- Scenes should be placed in `Assets/Scenes/` or appropriate subfolder
- Scene names should be descriptive and follow project naming conventions
- New scenes start empty - you'll need to add GameObjects
- Scene is automatically loaded after creation
