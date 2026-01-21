# Testing

XCBuddy supports running unit tests via `xcodebuild test`.

## Running Tests

### Run All Tests

**Cmd+Shift+T** or **XCBuddy > Test**

Runs all tests in the selected test target.

## Test Results

The **XCBuddy Tests** tool window displays:
- Test pass/fail status
- Failure messages and locations
- Test duration

The layout adapts to window size:
- **Wide window**: Test list on left, log output on right
- **Narrow window**: Test list on top, log output below

Click failed tests to navigate to the test source.

## Test Targets

Tests run against the test target associated with your selected scheme. Ensure:
1. Your scheme includes a test target
2. The test target is configured in Xcode

## Troubleshooting

### Tests Not Found

- Verify the scheme has a test action configured
- Check test target membership in Xcode
- Ensure test files follow `*Tests.swift` naming

### Tests Fail to Build

Run **Build** first to see compiler errors. Test execution requires a successful build.
