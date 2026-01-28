# Create GameObject

Create a new GameObject in the current scene, optionally with a specific type or components.

Usage: `/create-gameobject <name> [type]`

Examples:
- `/create-gameobject Player`
- `/create-gameobject Ground Cube`
- `/create-gameobject Enemy`

## Tools Used

- `manage_gameobject` tool - Create GameObjects
- `manage_components` tool - Add components to GameObjects
- `editor_state` resource - Verify Unity is in edit mode
- `batch_execute` tool - For creating GameObject with multiple components efficiently

## Workflow

1. **Check Unity state:**
   - Use `editor_state` to verify Unity is in edit mode (not play mode)
   - Ensure a scene is loaded

2. **Create the GameObject:**
   - Use `manage_gameobject` tool to create the GameObject
   - Provide the GameObject name
   - If a type is specified (Cube, Sphere, Plane, etc.), create that primitive type
   - If no type specified, create an empty GameObject

3. **Add components (if needed):**
   - If specific components are mentioned or commonly needed, use `manage_components` to add them
   - Use `batch_execute` if adding multiple components

4. **Verify creation:**
   - Confirm the GameObject was created
   - Report its position and hierarchy
   - Inform the user of the GameObject's location in the scene

## Notes

- GameObjects can only be created in edit mode
- Primitive types: Cube, Sphere, Capsule, Cylinder, Plane, Quad
- New GameObjects are created at origin (0,0,0) by default
- Use `batch_execute` for multiple GameObject operations
