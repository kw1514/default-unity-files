# Refresh Assets

Refresh the Unity asset database to update asset imports and detect new files.

## Tools Used

- `refresh_unity` tool - Refresh Unity asset database
- `read_console` resource - Check for import errors after refresh

## Workflow

1. **Refresh assets:**
   - Use `refresh_unity` tool to refresh the asset database
   - This will reimport assets and update Unity's internal database

2. **Check for errors:**
   - Use `read_console` resource to check for any import errors
   - Look for warnings or errors related to asset import

3. **Report results:**
   - Inform the user that assets have been refreshed
   - Report any import errors or warnings found
   - Suggest fixes if errors are present

## Notes

- Use this when assets don't appear in Unity after file system changes
- Refresh can take a moment for large projects
- Check console after refresh for import issues
- Unity usually auto-refreshes, but manual refresh can help with issues
