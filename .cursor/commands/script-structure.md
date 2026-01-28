# Script Structure

Show the current organization of the Scripts folder and its subfolders.

## Tools Used

- `manage_asset` tool - Read folder structure
- File system reading - List directories and files in Assets/Scripts

## Workflow

1. **Check Scripts folder:**
   - Verify `Assets/Scripts/` exists
   - If it doesn't exist, inform the user

2. **Read folder structure:**
   - List all subfolders in `Assets/Scripts/`
   - Show the hierarchy and organization
   - Count scripts in each folder (if possible)

3. **Display structure:**
   - Show a tree view of the Scripts folder
   - Highlight organizational patterns (by feature, by system, by type, etc.)
   - Show any notable structure patterns

4. **Provide context:**
   - Explain the organizational pattern if clear
   - Suggest where new scripts should be placed based on structure
   - Note if structure follows standard Unity conventions

## Example Output

```
Scripts Folder Structure:
Assets/Scripts/
├── Controllers/
│   ├── PlayerController.cs
│   └── EnemyController.cs
├── Managers/
│   ├── GameManager.cs
│   └── UIManager.cs
└── Utilities/
    └── Helper.cs

Organization Pattern: By system/feature
```

## Notes

- Understanding script structure helps maintain organization
- Use this before creating new scripts to find the right location
- Follow existing patterns when adding new scripts
