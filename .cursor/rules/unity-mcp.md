---
description: Workflow guidance for using Unity MCP tools to manage Unity projects, assets, scenes, and scripts
globs:
alwaysApply: true
---

# Unity MCP Workflow Rules

## Before Starting Any Unity Operation

Always check the current Unity Editor state using `editor_state` resource to understand:
- What scene is currently loaded
- Whether Unity is in play mode (some operations require edit mode)
- Current selection context

Check `editor_selection` resource to see what objects are currently selected in the Unity Editor.

## Safety: Deletion Confirmation Required

**CRITICAL: Always confirm with the user before deleting anything.** This applies to all deletion operations:

- **Assets** (scripts, prefabs, materials, textures, models, sprites, etc.)
- **GameObjects** (in scenes or prefabs)
- **Components** (removing components from GameObjects)
- **Folders** (deleting folders and their contents)
- **Scenes** (deleting scene files)
- **Any other Unity project elements**

**Before performing any deletion:**
1. Clearly state what you intend to delete (name, path, type)
2. Ask the user to confirm the deletion
3. Wait for explicit user confirmation before executing the deletion
4. Never assume deletion is implied or proceed without confirmation

This safety rule applies regardless of context - even if the user asks to "remove" or "delete" something, always confirm the specific item(s) to be deleted before proceeding.

## Project Structure and Folder Organization

All Unity projects follow a standard folder structure in the `Assets` folder. When creating or placing assets, always use the correct folders and create them if they don't exist.

### Standard Root Folders (Always Present)

These folders must exist in every project:
- `Assets/Scenes/` - All scene files
- `Assets/Prefabs/` - All prefab assets
- `Assets/Scripts/` - All C# script files
- `Assets/UI Elements/` - All UI-related assets (Canvas, Buttons, Panels, etc.)

### Project Type Specific Folders

- **3D Projects**: `Assets/Models/` - 3D model files (FBX, OBJ, etc.)
- **2D Projects**: `Assets/Sprites/` - 2D sprite assets

### Folder Creation and Asset Placement Rules

1. **Before creating any asset**:
   - Check if the required root folder exists (e.g., `Assets/Scenes/`, `Assets/Prefabs/`)
   - If a root folder doesn't exist, create it first using `manage_asset`
   - Read the current folder structure to understand existing subfolder organization

2. **When placing assets**:
   - **Scenes** → `Assets/Scenes/` (or appropriate subfolder)
   - **Prefabs** → `Assets/Prefabs/` (or appropriate subfolder)
   - **Scripts** → `Assets/Scripts/` (or appropriate subfolder)
   - **Materials** → `Assets/Materials/` (create if needed, or place in appropriate asset-specific folder)
   - **Textures** → `Assets/Textures/` (create if needed, or place in appropriate asset-specific folder)
   - **3D Models** → `Assets/Models/` (or appropriate subfolder)
   - **2D Sprites** → `Assets/Sprites/` (or appropriate subfolder)
   - **UI Elements** → `Assets/UI Elements/` (or appropriate subfolder)

3. **Subfolder organization**:
   - Subfolders within root folders are project-specific and vary by project
   - Before creating new subfolders, read the existing folder structure to understand the project's organization pattern
   - Follow existing naming conventions and organizational patterns when adding new subfolders
   - If the project has a clear organizational pattern (e.g., by feature, by system, by type), maintain that pattern

4. **When in doubt**:
   - If you're unsure which folder to use for an asset, **ask the user for clarification** before creating or placing the asset
   - Don't guess - it's better to clarify than to place assets incorrectly

5. **Creating missing folders**:
   - Use `manage_asset` to create folders if they don't exist
   - Create folders in the correct hierarchy (e.g., `Assets/Scenes/Level1/` if needed)
   - Ensure all standard root folders exist before starting asset creation

## When Creating or Modifying Scripts

1. **For new scripts**: 
   - Ensure `Assets/Scripts/` folder exists (create it if needed using `manage_asset`)
   - Read existing `Assets/Scripts/` structure to understand subfolder organization
   - Place scripts in appropriate subfolders following the project's organization pattern
   - Use `create_script` tool to generate proper Unity script boilerplate with correct namespaces and class structure
   - If unsure about subfolder placement, ask the user for clarification

2. **For editing existing scripts**: 
   - Read the script file first to understand its current state
   - Use `script_apply_edits` for script modifications (preferred) or `apply_text_edits` for general file edits
   - Always call `validate_script` after making changes to catch compilation errors immediately
   - Check `read_console` resource if validation fails to see specific error messages

3. **Never mark a script as complete without validating it first**. Always verify compilation succeeds.

4. **Before deleting scripts**: Always confirm with the user (see "Safety: Deletion Confirmation Required"). Use `delete_script` tool only after explicit user confirmation.

## When Working with Scenes

1. **Before creating or modifying a scene**: 
   - Ensure `Assets/Scenes/` folder exists (create it if needed using `manage_asset`)
   - Read existing `Assets/Scenes/` structure to understand subfolder organization
   - When creating new scenes, place them in `Assets/Scenes/` or appropriate subfolder following the project's pattern
   - Use `manage_scene` to load the target scene if it's not already active
   - Use `find_gameobjects` to locate specific GameObjects before modifying them

2. **When creating or modifying GameObjects**:
   - Use `manage_gameobject` to create, modify, or delete GameObjects
   - **Before deleting GameObjects**: Always confirm with the user (see "Safety: Deletion Confirmation Required")
   - Use `manage_components` to add, remove, or modify components on GameObjects
   - **Before removing components**: Always confirm with the user (see "Safety: Deletion Confirmation Required")
   - Batch multiple GameObject operations using `batch_execute` for better performance

3. **After scene changes**: Always save the scene using `manage_scene` to persist changes.

## When Creating or Managing Assets

1. **Before creating assets**: 
   - Review the "Project Structure and Folder Organization" section above
   - Verify the correct root folder exists (create it if needed)
   - Read existing folder structure to understand subfolder organization
   - If unsure about folder placement, ask the user for clarification

2. **Use specific asset tools** when available:
   - `manage_material` for materials
   - `manage_texture` for textures
   - `manage_prefabs` for prefabs
   - `manage_shader` for shaders
   - `manage_vfx` for Visual Effect Graph assets
   - `manage_scriptable_object` for ScriptableObjects
   - `manage_asset` for general asset operations and folder creation
   - **Before deleting any assets**: Always confirm with the user (see "Safety: Deletion Confirmation Required")

3. **Asset locations**: 
   - Always place assets in the correct standard folders (see "Project Structure and Folder Organization")
   - Follow existing subfolder patterns when placing assets
   - Unity MCP handles `.meta` file generation automatically
   - Create folders using `manage_asset` if they don't exist before placing assets

4. **After creating assets**: Check `read_console` for any warnings or errors related to asset creation.

## Performance Optimization

**Always use `batch_execute` when performing multiple operations**. It's 10-100x faster than individual tool calls. Batch related operations together:
- Multiple GameObject creations or modifications
- Multiple component additions
- Multiple asset operations
- Scene modifications involving multiple objects

## Error Handling and Troubleshooting

1. **If any operation fails**:
   - Immediately check `read_console` resource to see Unity error messages
   - Check `editor_state` to verify Unity Editor is in the correct state (not in play mode if required)
   - Verify the operation is valid for the current Unity context

2. **If assets don't appear**:
   - Use `refresh_unity` to refresh the Unity asset database
   - Check console for import errors

3. **If scripts have compilation errors**:
   - Use `validate_script` to get detailed error information
   - Check `read_console` for full compilation error details
   - Fix errors before proceeding with other operations

## Multiple Unity Instances

If multiple Unity Editor instances are running:
1. Check `unity_instances` resource to see all available instances
2. Use instance format `Name@hash` (e.g., `MyProject@abc123`) to target specific instances
3. Specify the target instance when making operations if needed

## Testing Workflow

When asked to run tests or verify functionality:
1. Use `get_tests` resource to see available Unity tests
2. Use `run_tests` to execute tests
3. Use `get_test_job` to check test execution status
4. Check `read_console` for test results and any failures

## Editor Automation

When automating Unity Editor operations:
- Use `execute_menu_item` to trigger Unity menu commands programmatically
- Use `manage_editor` to control Unity Editor state and operations
- Check `menu_items` resource to see available Unity menu commands

## Prefab Workflow

When working with prefabs:
1. Ensure `Assets/Prefabs/` folder exists (create it if needed using `manage_asset`)
2. Read existing `Assets/Prefabs/` structure to understand subfolder organization
3. When creating new prefabs, place them in `Assets/Prefabs/` or appropriate subfolder following the project's pattern
4. Use `prefab_info` resource to get prefab asset information
5. Use `prefab_hierarchy` to understand prefab structure
6. Use `manage_prefabs` to create or modify prefab assets
7. Check `editor_prefab_stage` resource if working in prefab edit mode

## Project Information

When you need project context:
- Use `project_info` resource for Unity project details
- Use `project_tags` to see available tags
- Use `project_layers` to see available layers
- Use `gameobject` and `gameobject_components` resources to inspect GameObject details

## General Principles

1. **Always confirm deletions**: Never delete anything (assets, scripts, GameObjects, components, folders, etc.) without explicit user confirmation (see "Safety: Deletion Confirmation Required")
2. **Always verify operations**: After any operation, check console or editor state to confirm success
3. **Batch when possible**: Group related operations into `batch_execute` calls
4. **Validate scripts**: Never skip script validation after modifications
5. **Check context first**: Always understand current Unity state before making changes
6. **Use specific tools**: Prefer specific asset management tools over general ones when available
