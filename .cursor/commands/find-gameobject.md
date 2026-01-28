# Find GameObject

Find GameObjects by name in the current scene.

Usage: `/find-gameobject <name>`

## Tools Used

- `find_gameobjects` tool - Search for GameObjects in the scene
- `gameobject` resource - Get detailed information about found GameObjects
- `gameobject_components` resource - Get components on found GameObjects

## Workflow

1. **Search for GameObjects:**
   - Use `find_gameobjects` tool with the search name
   - The tool supports partial matches and case-insensitive search
   - Get all matching GameObjects

2. **Get GameObject details:**
   - For each found GameObject, use `gameobject` resource to get:
     - Position, rotation, scale
     - Hierarchy path
     - Active state
   - Use `gameobject_components` to get component list

3. **Display results:**
   - Show count of matching GameObjects
   - List each GameObject with:
     - Full name and hierarchy path
     - Position
     - Key components
   - If no matches found, inform the user

## Example Output

```
Found 2 GameObjects matching "Player":
1. Player
   - Path: Scene/Player
   - Position: (0, 1, 0)
   - Components: Transform, Rigidbody, PlayerController

2. PlayerSpawn
   - Path: Scene/Managers/PlayerSpawn
   - Position: (0, 0, 0)
   - Components: Transform
```

## Notes

- Search is case-insensitive and supports partial matches
- Shows all GameObjects matching the search term
- Use this before modifying GameObjects to ensure you have the right one
