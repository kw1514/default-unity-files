# Fix Script Errors

Check Unity console for script compilation errors and attempt to fix them automatically.

## Tools Used

- `read_console` resource - Get Unity console errors
- `validate_script` tool - Validate specific scripts
- `find_in_file` tool - Search for problematic code patterns
- `script_apply_edits` tool - Apply fixes to scripts

## Workflow

1. **Check Unity console:**
   - Use `read_console` resource to get all errors
   - Filter for script compilation errors (CS errors)
   - Identify the affected script files

2. **Analyze errors:**
   - Read each script with errors
   - Identify common issues:
     - Missing using statements
     - Undefined types or namespaces
     - Syntax errors
     - Missing semicolons or brackets
     - Type mismatches

3. **Apply fixes:**
   - For each error, determine the fix
   - Use `script_apply_edits` to apply corrections
   - Common fixes:
     - Add missing `using` statements
     - Fix typos in type names
     - Correct syntax errors
     - Add missing brackets or semicolons

4. **Validate fixes:**
   - Use `validate_script` on each fixed script
   - Check `read_console` again to verify errors are resolved
   - If errors persist, report them to the user with suggestions

5. **Report results:**
   - List all errors found
   - Show which errors were fixed
   - Report any errors that couldn't be automatically fixed
   - Suggest manual fixes for complex issues

## Notes

- Not all errors can be automatically fixed
- Always validate scripts after applying fixes
- Complex errors may require user intervention
- Check Unity console for full error context
