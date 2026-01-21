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

## Settings

Configure XCBuddy via **Settings > Tools > XCBuddy**:

- SDK path configuration
- Build settings
- LSP options
