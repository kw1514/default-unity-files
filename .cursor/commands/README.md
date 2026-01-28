# Unity Slash Commands Directory

This directory contains slash commands for Unity development using Unity MCP tools. Commands can be invoked in Cursor chat using `/command-name`.

## Status & Diagnostics

- `/unity-status` - Check Unity Editor state (play mode, active scene, selection)
- `/unity-console` - Read Unity console for errors/warnings
- `/unity-selection` - Show currently selected GameObjects in Unity
- `/unity-project-info` - Display project information (tags, layers, Unity version)

## Script Management

- `/create-script <name>` - Create a new C# script with proper Unity boilerplate
- `/validate-script <path>` - Validate a script for compilation errors
- `/fix-script-errors` - Check console and fix script compilation errors
- `/script-structure` - Show the current Scripts folder organization

## Scene Management

- `/load-scene <name>` - Load a specific scene in Unity
- `/save-scene` - Save the currently active scene
- `/create-scene <name>` - Create a new scene file
- `/scene-info` - Show information about the current scene

## GameObject Commands

- `/create-gameobject <name> [type]` - Create a GameObject (optionally with specific type)
- `/find-gameobject <name>` - Find GameObjects by name in the scene
- `/selected-components` - Show components on currently selected GameObject(s)

## Asset Management

- `/create-prefab <name>` - Create a prefab from selected GameObject
- `/create-material <name>` - Create a new material
- `/asset-structure` - Show the Assets folder structure
- `/refresh-assets` - Refresh Unity asset database

## Testing Commands

- `/run-tests` - Run all Unity tests
- `/test-status` - Check test execution status
- `/list-tests` - Show available Unity tests

## Quick Workflow Commands

- `/setup-standard-folders` - Ensure all standard Unity folders exist (Scenes, Prefabs, Scripts, etc.)
- `/batch-validate-scripts` - Validate all scripts in the project
- `/clean-console` - Clear Unity console (via editor automation)
