# Create Material

Create a new material asset in the Unity project.

Usage: `/create-material <material-name>`

## Tools Used

- `manage_material` tool - Create material assets
- `manage_asset` tool - Ensure Materials folder exists (or create if needed)
- `read_console` resource - Check for material creation errors

## Workflow

1. **Check Materials folder:**
   - Check if `Assets/Materials/` folder exists
   - If it doesn't exist, create it using `manage_asset`
   - Read existing folder structure to understand organization
   - Some projects organize materials in asset-specific folders

2. **Determine material path:**
   - Check if material name already exists
   - Determine appropriate location
   - Follow existing project organization patterns
   - If unsure about placement, ask the user

3. **Create the material:**
   - Use `manage_material` tool to create the material
   - Provide the material name and path
   - The material will be created with default Unity material settings

4. **Verify creation:**
   - Check `read_console` for any errors
   - Confirm the material file exists
   - Report success to the user

5. **Optional setup:**
   - Ask if user wants to configure material properties (color, shader, etc.)
   - If yes, use `manage_material` to set properties

## Notes

- Materials should be placed in `Assets/Materials/` or appropriate folder
- New materials use Standard shader by default
- Materials can be configured after creation
- Use this before assigning materials to GameObjects
