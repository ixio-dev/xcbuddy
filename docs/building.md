# Building & Running

XCBuddy integrates with `xcodebuild` to build, run, and manage Xcode projects.

## Build Commands

### Build Project

**Cmd+Shift+B** or **XCBuddy > Build**

Builds the currently selected scheme and target. Output appears in the **XCBuddy Build** tool window.

### Build for Indexing

**XCBuddy > Build for Indexing**

Runs a build specifically to generate index data for SourceKit-LSP. Required for full code intelligence.

### Run

**Cmd+Shift+R** or **XCBuddy > Run**

Builds and launches the app on the selected device/simulator.

## Clean Commands

### Clean Build

**XCBuddy > Clean Build**

Runs `xcodebuild clean` for the current scheme.

### Clean Derived Data

**XCBuddy > Clean Derived Data**

Deletes the DerivedData folder for this project. Use when:
- Index seems corrupted
- Build artifacts cause issues
- Starting fresh

## Build Output

The **XCBuddy Build** tool window shows:
- Build progress and phases
- Compiler errors and warnings with file links
- Build duration

The layout adapts to window size:
- **Wide window**: Issue list on left, console output on right
- **Narrow window**: Issue list on top, console output below

Click error messages to jump to the source location.

## Device Selection

Use the **XCBuddy Devices** tool window to select:
- iOS Simulators
- Connected physical devices
- macOS (for Mac apps)

The selected device is used for **Run** commands.

## Scheme Selection

Projects with multiple schemes show a scheme selector. Select the scheme before building to target specific configurations.

## Deploy to Applications (macOS)

**XCBuddy > Deploy to Applications**

For macOS apps, quickly builds and copies to `/Applications`:
1. Builds in Release configuration
2. Copies the `.app` to `/Applications`
3. Notifies on completion

Useful for testing locally before full [release distribution](releasing.md).

## Open in Xcode

**XCBuddy > Open in Xcode** or right-click menu

Opens the project in Xcode for tasks requiring the full Xcode IDE.

## See Also

- [Device Management](devices.md) - Selecting devices for Run
- [Releasing](releasing.md) - Archive and distribute macOS apps
- [TestFlight](testflight.md) - Upload iOS apps
