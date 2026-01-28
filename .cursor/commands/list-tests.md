# List Tests

Show all available Unity tests in the project.

## Tools Used

- `get_tests` resource - Get list of available Unity tests

## Workflow

1. **Get test list:**
   - Use `get_tests` resource to retrieve all available tests
   - This returns all test methods and test classes

2. **Organize and display:**
   - Group tests by test class
   - Show test method names
   - Count total tests
   - Show test organization structure

3. **Display results:**
   - List all test classes
   - Under each class, list test methods
   - Show total test count
   - Highlight any test categories or attributes

## Example Output

```
Available Unity Tests (15 total):

PlayerControllerTests (5 tests)
  - TestMovement
  - TestJump
  - TestHealth
  - TestDeath
  - TestRespawn

GameManagerTests (4 tests)
  - TestGameStart
  - TestGamePause
  - TestGameEnd
  - TestScore

UIManagerTests (3 tests)
  - TestMenuShow
  - TestMenuHide
  - TestButtonClick

UtilityTests (3 tests)
  - TestMathHelper
  - TestStringHelper
  - TestArrayHelper
```