# Signing

XCBuddy provides visibility into your code signing setup via the Signing tool window.

## XCBuddy Signing Tool Window

Open via **View > Tool Windows > XCBuddy Signing**.

Displays two sections:
- **Certificates** - Your signing identities from Keychain
- **Provisioning Profiles** - Installed profiles

## Certificates

Shows all code signing certificates in your Keychain:
- Developer ID Application (macOS distribution)
- Apple Development (development)
- Apple Distribution (App Store)

Each certificate displays:
- Name and type
- Team ID
- Expiration date
- Status indicator (valid/expiring soon/expired)

## Provisioning Profiles

Lists profiles from `~/Library/MobileDevice/Provisioning Profiles`:
- Profile name
- App ID
- Team information
- Platform (iOS, macOS, etc.)
- Device count (for development profiles)
- Expiration date

**Double-click** a profile to reveal it in Finder.

## Status Indicators

Certificates and profiles show expiration status:
- **Green checkmark** - Valid
- **Yellow warning** - Expiring within 30 days
- **Red error** - Expired

## Settings

Configure signing preferences in **Settings > Tools > XCBuddy**:
- Default signing identity
- Automatic vs manual signing
- Team selection

These settings are used by [Release](releasing.md) and [TestFlight](testflight.md) workflows.

## See Also

- [Releasing](releasing.md) - Using certificates for macOS distribution
- [TestFlight](testflight.md) - Using profiles for iOS distribution
