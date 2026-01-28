# Scene Info

Show detailed information about the currently active scene.

## Tools Used

- `editor_state` resource - Get active scene information
- `find_gameobjects` tool - Find GameObjects in the scene
- `manage_scene` tool - Get scene details

## Workflow

1. **Get scene state:**
   - Use `editor_state` to get:
     - Active scene name
     - Scene path
     - Scene status

2. **Get scene contents:**
   - Use `find_gameobjects` to find all GameObjects in the scene
   - Get the hierarchy structure
   - Count total GameObjects

3. **Display scene information:**
   - Scene name and path
   - Total GameObject count
   - Top-level GameObjects (root objects)
   - Scene hierarchy overview (if not too large)

4. **Provide context:**
   - Show if scene is saved or has unsaved changes
   - Display any notable scene characteristics
   - List important GameObjects (Cameras, Managers, etc.)

## Example Output

```
Scene Information:
- Name: MainMenu
- Path: Assets/Scenes/MainMenu.unity
- Total GameObjects: 15
- Root Objects:
  - Canvas
  - EventSystem
  - Main Camera
  - GameManager
```