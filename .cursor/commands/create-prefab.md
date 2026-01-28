# Create Prefab

Create a prefab from the currently selected GameObject in Unity.

Usage: `/create-prefab <prefab-name>`

## Tools Used

- `editor_selection` resource - Get selected GameObject
- `manage_prefabs` tool - Create prefab assets
- `manage_asset` tool - Ensure Prefabs folder exists
- `prefab_info` resource - Verify prefab creation

## Workflow

1. **Check selection:**
   - Use `editor_selection` to get currently selected GameObject
   - If nothing is selected, inform the user they must select a GameObject first
   - If multiple objects selected, ask which one to use or use the first

2. **Check Prefabs folder:**
   - Verify `Assets/Prefabs/` folder exists
   - If it doesn't exist, create it using `manage_asset`
   - Read existing `Assets/Prefabs/` structure to understand subfolder organization

3. **Determine prefab path:**
   - Check if prefab name already exists
   - Determine appropriate location (root Prefabs folder or subfolder)
   - Follow existing project organization patterns
   - If unsure about placement, ask the user

4. **Create the prefab:**
   - Use `manage_prefabs` tool to create the prefab
   - Provide the GameObject path and prefab save path
   - The prefab will be created from the selected GameObject

5. **Verify creation:**
   - Use `prefab_info` resource to confirm prefab was created
   - Check that the prefab file exists
   - Report success to the user

## Notes

- A GameObject must be selected in Unity to create a prefab
- Prefabs should be placed in `Assets/Prefabs/` or appropriate subfolder
- The original GameObject in the scene becomes a prefab instance
- Prefab creation works in edit mode only
