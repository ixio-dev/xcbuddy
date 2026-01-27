# Target Selection

XCBuddy provides target-based filtering to focus on specific parts of large Xcode projects.

## XCBuddy Targets Tool Window

Open via **View > Tool Windows > XCBuddy Targets** or click the XCBuddy icon in the right sidebar.

Lists all native targets from your `.xcodeproj`:
- App targets
- Framework targets
- Test targets
- Extension targets

## Filtering by Target

Select a target to filter the project view:
- Files belonging to the target display normally
- Files not in the target appear grayed out
- Helps focus on relevant source files

## How It Works

XCBuddy parses the `.pbxproj` file to determine file membership:

1. Identifies `PBXNativeTarget` entries
2. Follows build phases to `PBXSourcesBuildPhase`
3. Maps files via `PBXBuildFile` and `PBXFileReference`

## File Membership Status

The status bar shows target membership for the current file:
- Which targets include this file
- Click to see full membership list

### Show Target Membership Action

Right-click a file > **Show Target Membership** to see all targets containing that file.

## Use Cases

- **Large projects** - Focus on your current feature's target
- **Multi-target apps** - Distinguish between main app and extensions
- **Shared code** - See which files are shared across targets

## See Also

- [Building](building.md) - Build selected target
- [Testing](testing.md) - Test target selection
