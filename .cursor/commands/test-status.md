# Test Status

Check the status of currently running or recently completed Unity tests.

## Tools Used

- `get_test_job` tool - Get test execution status
- `read_console` resource - Get test output and results

## Workflow

1. **Check test job status:**
   - Use `get_test_job` tool to get current test execution status
   - This shows if tests are running, completed, or queued

2. **Get test results:**
   - If tests are completed, use `read_console` to get results
   - Parse test output for pass/fail information

3. **Display status:**
   - Show current test execution state:
     - Running - tests are currently executing
     - Completed - tests have finished
     - Queued - tests are waiting to run
     - Not Running - no tests are executing
   - If completed, show summary of results
   - If running, show that tests are in progress

4. **Provide next steps:**
   - If tests are running, suggest waiting or checking again
   - If completed, show results summary
   - If failed, suggest using `/run-tests` to see full output

## Example Output

```
Test Status: Completed

Results:
- Total: 15 tests
- Passed: 13
- Failed: 2
- Duration: 2.3s
```