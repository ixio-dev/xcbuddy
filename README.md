# XCBuddy

XCBuddy is an IntelliJ Platform plugin that brings Swift and Xcode project support to JetBrains IDEs. It integrates SourceKit-LSP for intelligent code assistance and lets you open `.xcodeproj` bundles directly as projects.

## Features

- **Code Intelligence** - Completion, go-to-definition, find usages, hover docs via SourceKit-LSP
- **Syntax Highlighting** - Swift, .pbxproj, .plist, .entitlements, .xcstrings files
- **Build & Run** - Build, run, and test Xcode projects directly from the IDE
- **Target Selection** - Filter project view by Xcode target
- **Device Management** - Select simulators and devices for running your app
- **Swift Packages** - View and manage SPM dependencies
- **Apple Documentation** - Quick access to Apple Developer docs

## Documentation

| Topic | Description |
|-------|-------------|
| [Setup](docs/setup.md) | Requirements and installation |
| [Code Intelligence](docs/lsp-support.md) | LSP features and troubleshooting |
| [Building & Running](docs/building.md) | Build, run, and clean commands |
| [Testing](docs/testing.md) | Running unit tests |
| [Target Selection](docs/target-selection.md) | Filtering by Xcode target |
| [Swift Packages](docs/swift-packages.md) | SPM integration |

## Quick Start

1. Install XCBuddy from the JetBrains Marketplace
2. Ensure Xcode is installed (provides `sourcekit-lsp`)
3. Open your `.xcodeproj` or folder containing `Package.swift`
4. Build for indexing: **XCBuddy > Build for Indexing**
