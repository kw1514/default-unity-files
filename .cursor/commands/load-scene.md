# Load Scene

Load a specific scene in the Unity Editor.

Usage: `/load-scene <scene-name>`

## Tools Used

- `manage_scene` tool - Load scenes in Unity
- `editor_state` resource - Verify scene was loaded successfully
- `manage_asset` tool - Check if scene exists

## Workflow

1. **Check Unity state:**
   - Use `editor_state` to check if Unity is in play mode
   - If in play mode, inform the user that scenes can only be loaded in edit mode

2. **Find the scene:**
   - Check if the scene exists in `Assets/Scenes/`
   - If scene name doesn't include extension, search for `.unity` files
   - If scene not found, list available scenes

3. **Load the scene:**
   - Use `manage_scene` tool to load the scene
   - Specify the scene path (e.g., `Assets/Scenes/MainMenu.unity`)

4. **Verify loading:**
   - Use `editor_state` to confirm the scene is now active
   - Report success to the user

## Notes

- Scenes can only be loaded when Unity is not in play mode
- Scene names can be provided with or without `.unity` extension
- If scene doesn't exist, suggest available scenes
- Scene changes are not automatically saved - use `/save-scene` to save
