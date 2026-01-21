# Swift Packages

XCBuddy provides Swift Package Manager integration for both standalone packages and Xcode projects with SPM dependencies.

## XCBuddy Packages Tool Window

Open via **View > Tool Windows > XCBuddy Packages** or click the Packages icon in the right sidebar.

Displays:
- Package dependencies
- Package products
- Dependency versions

## Supported Project Types

### Package.swift Projects

Open a folder containing `Package.swift`. XCBuddy:
- Parses package structure
- Identifies targets and dependencies
- Enables SourceKit-LSP for the package

### Xcode Projects with SPM

Xcode projects using Swift packages show their dependencies in the Packages tool window.

## Package Resolution

When dependencies change:
1. Xcode/SPM resolves packages automatically
2. Build the project to update the index
3. Code intelligence updates with new APIs

## Adding Sparkle Framework

XCBuddy can automatically add the Sparkle auto-update framework to macOS apps.

### Via Menu

**XCBuddy > Add Sparkle Framework**

This adds:
- Package dependency to `Package.swift` or Xcode project
- Target dependency to executable targets

### What Gets Added

For `Package.swift` projects:

```swift
// In dependencies:
.package(
    url: "https://github.com/sparkle-project/Sparkle",
    .upToNextMajor(from: "2.6.0")
)

// In executableTarget dependencies:
.product(name: "Sparkle", package: "Sparkle")
```

### Next Steps After Adding

1. Add `SUFeedURL` to your `Info.plist`
2. Generate signing keys with Sparkle's `generate_keys` tool
3. Disable App Sandbox in entitlements (or configure network exceptions)

## Troubleshooting

### Missing Package Completions

Run **Build for Indexing** to ensure package symbols are indexed.

### Package Resolution Fails

Use Xcode to resolve package issues, then return to your JetBrains IDE. Complex resolution scenarios may require Xcode's package management UI.
