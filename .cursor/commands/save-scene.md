# Save Scene

Save the currently active scene in Unity.

## Tools Used

- `manage_scene` tool - Save the active scene
- `editor_state` resource - Get current scene information
- `read_console` resource - Check for save errors

## Workflow

1. **Check current scene:**
   - Use `editor_state` to get the active scene name
   - Verify a scene is loaded (not in empty state)

2. **Save the scene:**
   - Use `manage_scene` tool to save the current scene
   - The tool will save all changes to the scene file

3. **Verify save:**
   - Check `read_console` for any save errors
   - Confirm save was successful

4. **Report to user:**
   - Inform user that the scene has been saved
   - Show the scene name that was saved

## Notes

- Always save scenes after making significant changes
- Unity may prompt to save on close, but it's better to save explicitly
- Scene must be loaded (not empty) to save
- Save operations work in edit mode only
