# Create Script

Create a new C# script with proper Unity boilerplate and namespace structure.

Usage: `/create-script <script-name>`

## Tools Used

- `create_script` tool - Create a new Unity script with proper structure
- `manage_asset` tool - Ensure Scripts folder exists
- `validate_script` tool - Validate the created script

## Workflow

1. **Before creating the script:**
   - Check if `Assets/Scripts/` folder exists using `manage_asset`
   - If it doesn't exist, create it first
   - Read existing `Assets/Scripts/` structure to understand subfolder organization
   - Determine appropriate subfolder placement based on project patterns

2. **Create the script:**
   - Use `create_script` tool with:
     - Script name (from user input)
     - Appropriate folder path (following project structure)
     - Proper namespace and class structure

3. **Validate the script:**
   - Use `validate_script` tool to ensure compilation succeeds
   - Check for any immediate errors

4. **Confirm completion:**
   - Inform the user of the script location
   - Report validation status
   - If validation fails, check `read_console` and report errors

## Notes

- Scripts should be placed in `Assets/Scripts/` or appropriate subfolder
- Follow existing project organization patterns
- Always validate scripts after creation
- If unsure about subfolder placement, ask the user for clarification
