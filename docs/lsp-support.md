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

### No Completions

SourceKit-LSP requires build index data. Run **Build for Indexing** to generate it.

### Stale Diagnostics

After major changes, clean and rebuild:
1. **XCBuddy > Clean Derived Data**
2. **XCBuddy > Build for Indexing**
