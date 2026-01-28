# Selected Components

Show components attached to currently selected GameObject(s) in Unity.

## Tools Used

- `editor_selection` resource - Get selected GameObjects
- `gameobject_components` resource - Get components on GameObjects
- `gameobject` resource - Get GameObject details

## Workflow

1. **Check selection:**
   - Use `editor_selection` to get currently selected GameObjects
   - If nothing is selected, inform the user

2. **Get components:**
   - For each selected GameObject, use `gameobject_components` resource to get:
     - All attached components
     - Component types
     - Component order

3. **Get GameObject details:**
   - Use `gameobject` resource to get basic GameObject info
   - This provides context for the components

4. **Display components:**
   - Show GameObject name
   - List all components with their types
   - Show component order (important for execution order)
   - Highlight important components (MonoBehaviours, Colliders, etc.)

## Example Output

```
Selected GameObject: Player

Components:
1. Transform
2. Rigidbody
   - Mass: 1
   - Use Gravity: true
3. Capsule Collider
   - Radius: 0.5
   - Height: 2
4. PlayerController (MonoBehaviour)
5. Health (MonoBehaviour)
```