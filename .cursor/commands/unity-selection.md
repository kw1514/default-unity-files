# Unity Selection

Show currently selected GameObjects in the Unity Editor.

## Tools Used

- `editor_selection` resource - Get currently selected GameObjects
- `gameobject` resource - Get detailed information about specific GameObjects
- `gameobject_components` resource - Get components on selected GameObjects

## Workflow

1. Use `editor_selection` resource to get:
   - List of selected GameObject names
   - Selection count
   - Selection paths/hierarchies

2. If objects are selected, use `gameobject` and `gameobject_components` resources to get:
   - GameObject details (position, rotation, scale)
   - Component list for each selected object
   - Hierarchy information

3. Display to the user:
   - Number of selected objects
   - Names of selected objects
   - Key components on selected objects
   - If nothing is selected, inform the user

## Example Output

```
Unity Selection:
- Selected: 1 object
- GameObject: Player
  - Position: (0, 1, 0)
  - Components: Transform, Rigidbody, PlayerController, Collider
```
