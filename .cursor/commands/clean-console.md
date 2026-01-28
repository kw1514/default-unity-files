# Clean Console

Clear the Unity console of all messages (errors, warnings, logs).

## When to Use

Use this command to:
- Clear the Unity console
- Remove old messages
- Start with a clean console
- Focus on new errors/warnings

## Tools Used

- `execute_menu_item` tool - Execute Unity menu commands
- `manage_editor` tool - Control Unity Editor operations
- `read_console` resource - Verify console is cleared

## Workflow

1. **Clear console:**
   - Use `execute_menu_item` tool to execute Unity's "Clear" menu item
   - The menu path is typically: `Window > General > Console` then clear button
   - Alternatively, use `manage_editor` if it supports console clearing
   - Unity's console clear command: `Window/General/Console` with clear action

2. **Verify clearing:**
   - Use `read_console` resource to verify console is empty
   - Confirm no messages remain

3. **Report results:**
   - Inform user that console has been cleared
   - Note that new messages will appear as they occur

## Notes

- Clears all console messages (errors, warnings, logs)
- Useful for focusing on new issues
- Console will populate again as Unity generates messages
- Some Unity versions may require specific menu paths

## Alternative Approach

If direct console clearing isn't available via MCP tools:
- Inform the user that console clearing may need to be done manually in Unity
- Suggest using Unity's console window clear button
- Or use `read_console` to show current messages, then note they can be cleared manually
