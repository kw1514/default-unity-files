# Batch Validate Scripts

Validate all C# scripts in the project for compilation errors.

## Tools Used

- `validate_script` tool - Validate individual scripts
- `find_in_file` tool - Find all .cs files in the project
- `read_console` resource - Get compilation errors
- `batch_execute` tool - Validate multiple scripts efficiently (if supported)

## Workflow

1. **Find all scripts:**
   - Search for all `.cs` files in `Assets/Scripts/` directory
   - Get list of all script files to validate

2. **Validate scripts:**
   - For each script, use `validate_script` tool
   - If `batch_execute` supports script validation, use it for better performance
   - Otherwise, validate scripts individually

3. **Collect results:**
   - Track which scripts passed validation
   - Track which scripts failed validation
   - Collect error messages for failed scripts

4. **Check console:**
   - Use `read_console` resource to get all compilation errors
   - This provides comprehensive error information

5. **Report results:**
   - Show total script count
   - Show passed count
   - Show failed count
   - List all scripts with errors:
     - Script path
     - Error count
     - Key error messages
   - Provide summary and next steps

## Example Output

```
Script Validation Results:
- Total Scripts: 25
- Passed: 23
- Failed: 2

Scripts with Errors:
1. Assets/Scripts/Controllers/PlayerController.cs
   - 2 errors
   - CS0246: Type 'Health' not found
   - CS0103: 'transform' does not exist

2. Assets/Scripts/Managers/GameManager.cs
   - 1 error
   - CS0116: Namespace cannot contain members
```