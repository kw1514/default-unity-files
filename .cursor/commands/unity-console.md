# Unity Console

Read the Unity console to check for errors, warnings, and log messages.

## Tools Used

- `read_console` resource - Read Unity console messages

## Workflow

1. Use `read_console` resource to retrieve:
   - All console messages (errors, warnings, logs)
   - Error count
   - Warning count
   - Most recent messages

2. Display the console output to the user, highlighting:
   - Errors (if any) - show these prominently
   - Warnings (if any) - show these clearly
   - Recent log messages (if relevant)

3. If errors are present:
   - Summarize the error count
   - List the most critical errors
   - Suggest next steps (e.g., use `/fix-script-errors`)

## Example Output

```
Unity Console:
- Errors: 2
- Warnings: 5
- Recent Errors:
  1. CS0246: The type or namespace name 'PlayerController' could not be found
  2. CS0103: The name 'transform' does not exist in the current context
```
