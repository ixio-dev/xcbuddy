# XCBuddy

XCBuddy is an IntelliJ Platform plugin that brings Swift and Xcode project support to JetBrains IDEs. It integrates SourceKit-LSP for intelligent code assistance and lets you open `.xcodeproj` bundles directly as projects.

## Features

- **Code Intelligence** - Completion, go-to-definition, find usages, hover docs via SourceKit-LSP
- **Swift Toolchain SDK** - Register and manage Swift toolchains as project SDKs
- **Syntax Highlighting** - Swift, .pbxproj, .plist, .entitlements, .xcstrings files
- **Build & Run** - Build, run, and test Xcode projects directly from the IDE
- **Target Selection** - Filter project view by Xcode target
- **Device Management** - Simulator control, screenshots, screen recording
- **Swift Packages** - View and manage SPM dependencies
- **Signing & Certificates** - View certificates and provisioning profiles
- **Release Distribution** - Archive, notarize, and create DMG for macOS apps
- **TestFlight Upload** - Archive and upload iOS/tvOS/watchOS/visionOS apps
- **Deploy to Applications** - Quick local deployment for macOS apps
- **Sparkle Integration** - Add auto-update support to macOS apps
- **Apple Documentation** - Quick access to Apple Developer docs

## Documentation

| Topic | Description |
|-------|-------------|
| [Setup](docs/setup.md) | Requirements and installation |
| [Code Intelligence](docs/lsp-support.md) | LSP features and troubleshooting |
| [Building & Running](docs/building.md) | Build, run, and clean commands |
| [Testing](docs/testing.md) | Running unit tests |
| [Target Selection](docs/target-selection.md) | Filtering by Xcode target |
| [Device Management](docs/devices.md) | Simulators and device control |
| [Swift Packages](docs/swift-packages.md) | SPM integration |
| [Signing](docs/signing.md) | Certificates and provisioning profiles |
| [Releasing](docs/releasing.md) | Archive, notarize, and distribute macOS apps |
| [TestFlight](docs/testflight.md) | Upload to TestFlight |
| [Sparkle](docs/sparkle.md) | Auto-update framework integration |

## Quick Start

1. Install XCBuddy from the JetBrains Marketplace
2. Ensure Xcode is installed (provides `sourcekit-lsp`)
3. Open your `.xcodeproj` or folder containing `Package.swift`
4. Build for indexing: **XCBuddy > Build for Indexing**
