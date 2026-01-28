# Unity Status

Check the current state of the Unity Editor including play mode status, active scene, and current selection.

## Tools Used

- `editor_state` resource - Get Unity Editor state information
- `editor_selection` resource - Get currently selected GameObjects

## Workflow

1. Use `editor_state` resource to retrieve:
   - Current scene name and path
   - Play mode status (playing/paused/stopped)
   - Editor state information
   - Any other relevant editor state data

2. Use `editor_selection` resource to get:
   - Currently selected GameObject names
   - Selection count
   - Selected object details

3. Display a clear summary to the user showing:
   - Active scene name
   - Play mode status
   - Selected objects (if any)
   - Any warnings or important state information

## Example Output

```
Unity Editor Status:
- Active Scene: MainMenu
- Play Mode: Stopped
- Selected Objects: Player (1 object)
```
