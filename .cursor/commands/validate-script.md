# Validate Script

Validate a C# script for compilation errors and syntax issues.

Usage: `/validate-script <script-path>`

## Tools Used

- `validate_script` tool - Validate script compilation
- `read_console` resource - Get detailed error messages if validation fails

## Workflow

1. **Validate the script:**
   - Use `validate_script` tool with the script path
   - Wait for validation results

2. **Check results:**
   - If validation succeeds, inform the user
   - If validation fails:
     - Use `read_console` resource to get detailed error messages
     - Display all compilation errors clearly
     - List line numbers and error descriptions
     - Suggest fixes if possible

3. **Report to user:**
   - Show validation status (success/failure)
   - Display any errors with context
   - Provide next steps if errors are found
