# Run Tests

Execute all Unity tests in the project.

## Tools Used

- `run_tests` tool - Execute Unity tests
- `get_test_job` tool - Check test execution status
- `read_console` resource - Get test results and output

## Workflow

1. **Check available tests:**
   - Optionally use `get_tests` resource to see what tests are available
   - This helps set expectations

2. **Run tests:**
   - Use `run_tests` tool to execute all tests
   - The tool will start test execution

3. **Monitor execution:**
   - Use `get_test_job` tool to check test execution status
   - Wait for tests to complete
   - Check status periodically until complete

4. **Get results:**
   - Use `read_console` resource to get test results
   - Parse test output for pass/fail information
   - Count passed and failed tests

5. **Report results:**
   - Display test execution summary
   - Show passed test count
   - Show failed test count
   - List any failed tests with error messages
   - Provide next steps if tests failed

## Example Output

```
Test Execution Results:
- Total Tests: 15
- Passed: 13
- Failed: 2

Failed Tests:
1. PlayerControllerTests.TestMovement
   - Error: Assert.AreEqual failed. Expected: 5, Actual: 0
2. GameManagerTests.TestGameStart
   - Error: NullReferenceException
```