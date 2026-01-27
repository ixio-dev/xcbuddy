# TestFlight

XCBuddy can archive and upload iOS, tvOS, watchOS, and visionOS apps directly to TestFlight.

## Upload to TestFlight

**XCBuddy > Upload to TestFlight...**

Opens a dialog to configure the upload.

## Requirements

### App Store Connect API Key

TestFlight upload requires an App Store Connect API key:

1. Go to [App Store Connect > Users and Access > Integrations](https://appstoreconnect.apple.com/access/integrations)
2. Generate a new API key with **Developer** or **Admin** role
3. Download the `.p8` key file

### Configure in XCBuddy

**Settings > Tools > XCBuddy > TestFlight**:

- **Key ID** - From App Store Connect (e.g., `ABCD123456`)
- **Issuer ID** - From App Store Connect (UUID format)
- **Key File** - Path to downloaded `.p8` file

## Upload Steps

### 1. Archive

Creates an `.xcarchive` using `xcodebuild archive`.

### 2. Export for App Store

Exports an App Store-signed IPA from the archive.

### 3. Upload

Uses `altool` or `notarytool` to upload to App Store Connect.

## Platform Support

TestFlight upload is available for:
- iOS
- tvOS
- watchOS
- visionOS

For macOS apps, use [Release App](releasing.md) instead.

## Build Settings

Ensure your project has:
- Valid **App Store Distribution** certificate
- **App Store** provisioning profile
- Correct **Bundle Identifier** matching App Store Connect

## Troubleshooting

### "Missing App Store Connect API Key"

Configure the API key in **Settings > Tools > XCBuddy > TestFlight**.

### Upload Fails

- Verify API key permissions (needs Developer or Admin role)
- Check bundle ID matches App Store Connect
- Ensure provisioning profile is valid

### Archive Fails

Run **Build** first to check for compilation errors.

## See Also

- [Building](building.md) - Build configuration
- [Signing](signing.md) - Managing certificates and profiles
