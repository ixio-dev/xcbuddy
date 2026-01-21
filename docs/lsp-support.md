# Code Intelligence

XCBuddy integrates SourceKit-LSP to provide intelligent code assistance for Swift.

## Features

### Code Completion

Start typing to get context-aware suggestions including:
- Types, functions, and properties
- Parameter names and types
- Documentation snippets

### Go to Definition

Navigate to symbol definitions:
- **Cmd+Click** on a symbol
- **Cmd+B** with cursor on symbol
- Right-click > **Go to > Declaration**

### Find Usages

Find all references to a symbol:
- **Alt+F7** with cursor on symbol
- Right-click > **Find Usages**

### Hover Documentation

Hover over any symbol to see:
- Type signature
- Documentation comments
- Parameter descriptions

### Diagnostics

Real-time error and warning display:
- Inline error highlighting
- Error descriptions in editor gutter
- Quick fixes when available

## Status Bar Indicator

The LSP status appears in the bottom status bar:
- **Connected** - LSP is running and ready
- **Connecting** - LSP is starting up
- **Error** - Connection failed (click for details)

## Toolchain Selection

When a Swift SDK is configured as the project SDK, XCBuddy uses that toolchain's `sourcekit-lsp`:

1. **Project SDK** - Uses `{toolchain}/usr/bin/sourcekit-lsp`
2. **Fallback** - System `sourcekit-lsp` from PATH

This enables using different Swift versions per project. See [Setup > Swift Toolchain SDK](setup.md#swift-toolchain-sdk).

## Troubleshooting

### LSP Not Connecting

1. Verify `sourcekit-lsp` is in PATH:
   ```bash
   which sourcekit-lsp
   ```

2. Check Xcode is installed:
   ```bash
   xcode-select -p
   ```

3. Try building the project first:
   **XCBuddy > Build for Indexing**

4. If using a custom toolchain, ensure it's set as the project SDK

### No Completions

SourceKit-LSP requires build index data. Run **Build for Indexing** to generate it.

### Stale Diagnostics

After major changes, clean and rebuild:
1. **XCBuddy > Clean Derived Data**
2. **XCBuddy > Build for Indexing**
