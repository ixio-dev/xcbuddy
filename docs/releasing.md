# Releasing

XCBuddy provides a complete release workflow for macOS apps, from archiving to distribution.

## Release App

**XCBuddy > Release App...**

Opens a dialog to configure the release:

### Version

- **Current version** - Detected from your project
- **New version** - Auto-incremented, editable

### Release Notes

Pre-populated from git commits since the last tag. Edit as needed.

### Options

- **Create git tag** - Tags the release in git (e.g., `v1.2.3`)
- **Update version-history.md** - Appends release notes to history file

## Release Steps

The release process runs 7 steps:

### 1. Set Version

Updates version in your project configuration.

### 2. Archive

Runs `xcodebuild archive` to create an `.xcarchive`.

### 3. Export & Sign

Exports the app from the archive with your signing identity (Developer ID Application certificate).

### 4. Notarize

Submits the app to Apple for notarization. Requires:
- Valid Developer ID certificate
- Apple Developer account

### 5. Staple

Attaches the notarization ticket to the app for offline verification.

### 6. Create DMG

Optionally creates a `.dmg` disk image for distribution. Enable in **Settings > Tools > XCBuddy**.

### 7. Finalize

- Creates git tag (if enabled)
- Updates version history (if enabled)

## Output

On completion, XCBuddy shows:
- Version number
- Path to signed `.app`
- Path to `.dmg` (if created)

## Deploy to Applications

**XCBuddy > Deploy to Applications**

Quick local deployment for development:
1. Builds the app in Release configuration
2. Copies to `/Applications`

Useful for testing the release build locally before distribution.

## Requirements

- **Developer ID Application** certificate in Keychain
- **Apple Developer** account for notarization
- **Xcode** with command line tools

## Settings

Configure in **Settings > Tools > XCBuddy**:
- Signing identity
- Create DMG by default
- Notarization credentials

## Troubleshooting

### Notarization Fails

- Verify Developer ID certificate is valid
- Check Apple Developer account credentials
- Ensure app doesn't contain hardened runtime violations

### Code Signing Error

- Verify certificate in **XCBuddy Signing** tool window
- Check certificate hasn't expired
- Ensure Keychain access is granted

## See Also

- [Signing](signing.md) - Managing certificates and profiles
- [TestFlight](testflight.md) - iOS distribution
