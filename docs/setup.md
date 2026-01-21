# Setup

## Requirements

- **IntelliJ-based IDE** (IntelliJ IDEA, AppCode, etc.) version 2024.3+
- **Xcode** installed on macOS (provides `sourcekit-lsp`)
- **LSP4IJ plugin** (installed automatically as dependency)

## Installation

1. Open **Settings > Plugins**
2. Search for "XCBuddy"
3. Click **Install**
4. Restart the IDE

## Verifying SourceKit-LSP

XCBuddy uses SourceKit-LSP for code intelligence. Verify it's available:

```bash
which sourcekit-lsp
# Should output: /usr/bin/sourcekit-lsp or similar
```

If not found, ensure Xcode command line tools are installed:

```bash
xcode-select --install
```

## Opening Projects

### Xcode Projects (.xcodeproj)

Open any `.xcodeproj` bundle directly. XCBuddy will:
- Parse the project structure
- Enable Swift syntax highlighting
- Connect to SourceKit-LSP

### Swift Package Manager Projects

Open a folder containing `Package.swift`. XCBuddy detects the package and enables full support.

## First Steps After Opening

1. **Build for Indexing** - Run **XCBuddy > Build for Indexing** to generate index data
2. **Wait for LSP** - The status bar shows LSP connection state
3. **Select a Target** - Use the XCBuddy Targets tool window to filter files

## Swift Toolchain SDK

XCBuddy registers Swift toolchains as proper IntelliJ SDKs, enabling per-project toolchain selection.

### Adding a Swift SDK

1. Open **File > Project Structure > SDKs**
2. Click **+** and select **Swift Toolchain**
3. Select a `.xctoolchain` directory (Xcode default is auto-suggested)
4. The SDK is configured with version info and sourcekit-lsp path

### Detected Toolchain Locations

- `/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain`
- `/Library/Developer/Toolchains/*.xctoolchain`
- `~/Library/Developer/Toolchains/*.xctoolchain`

### Setting Project SDK

1. Open **File > Project Structure > Project**
2. Select a registered Swift toolchain from the SDK dropdown
3. SourceKit-LSP will use this toolchain's `sourcekit-lsp` binary

## Settings

Configure XCBuddy via **Settings > Tools > XCBuddy**:

- Build settings
- Signing configuration
- Device preferences
