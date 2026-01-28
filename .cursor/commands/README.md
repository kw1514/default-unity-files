# Unity Slash Commands Directory

This directory contains slash commands for Unity development using Unity MCP tools. Commands can be invoked in Cursor chat using `/command-name`.

**Note:** These commands are shortcuts for common operations. Comprehensive workflows for creating assets, managing scenes, and organizing projects are defined in `.cursor/rules/unity-mcp.md`, which is always applied. The AI agent will follow those rules automatically during normal operations.

## Status & Diagnostics
- `/unity-status` - Quick check of Unity Editor state (play mode, active scene, selection)
- `/unity-console` - Read Unity console for errors/warnings
- `/unity-selection` - Show currently selected GameObjects in Unity
- `/unity-project-info` - Display project information (tags, layers, Unity version)

## Script Management
- `/validate-script <path>` - Validate a script for compilation errors
- `/fix-script-errors` - Check console and fix script compilation errors
- `/batch-validate-scripts` - Validate all scripts in the project

## Scene Management
- `/load-scene <name>` - Load a specific scene in Unity
- `/save-scene` - Save the currently active scene
- `/scene-info` - Show information about the current scene

## GameObject Commands
- `/find-gameobject <name>` - Find GameObjects by name in the scene
- `/selected-components` - Show components on currently selected GameObject(s)

## Asset Management
- `/refresh-assets` - Refresh Unity asset database

## Testing Commands
- `/run-tests` - Run all Unity tests
- `/test-status` - Check test execution status
- `/list-tests` - Show available Unity tests

## Quick Workflow Commands
- `/setup-standard-folders` - Quick shortcut to create all standard Unity folders at once
- `/clean-console` - Clear Unity console (via editor automation)