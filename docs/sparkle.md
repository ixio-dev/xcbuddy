# Sparkle

XCBuddy helps integrate the [Sparkle](https://sparkle-project.org/) auto-update framework into macOS apps.

## Adding Sparkle

**XCBuddy > Add Sparkle Framework**

Adds Sparkle to your project via Swift Package Manager.

### What Gets Added

For **Package.swift** projects:

```swift
// Package dependency
.package(
    url: "https://github.com/sparkle-project/Sparkle",
    .upToNextMajor(from: "2.6.0")
)

// Target dependency
.product(name: "Sparkle", package: "Sparkle")
```

For **Xcode projects**, adds the same SPM dependency through the project file.

## XCBuddy Sparkle Tool Window

Open via **View > Tool Windows > XCBuddy Sparkle**.

Validates your Sparkle setup:
- Sparkle dependency present
- `SUFeedURL` configured
- Entitlements properly set
- Signing requirements met

## Setup Steps After Adding

### 1. Configure Feed URL

Add to your `Info.plist`:

```xml
<key>SUFeedURL</key>
<string>https://yoursite.com/appcast.xml</string>
```

### 2. Generate Signing Keys

Run Sparkle's key generation:

```bash
./Sparkle.framework/Versions/B/Resources/generate_keys
```

Store the private key securely; add the public key to your `Info.plist`:

```xml
<key>SUPublicEDKey</key>
<string>your-public-key</string>
```

### 3. Configure Entitlements

Sparkle requires network access. Either:
- Disable App Sandbox, or
- Add network client entitlement

### 4. Initialize Sparkle

In your app's initialization:

```swift
import Sparkle

let updaterController = SPUStandardUpdaterController(
    startingUpdater: true,
    updaterDelegate: nil,
    userDriverDelegate: nil
)
```

## Publishing Updates

1. Build your release using **XCBuddy > Release App...**
2. Generate appcast entry using Sparkle's `generate_appcast` tool
3. Upload app and update `appcast.xml`

## macOS Only

The Sparkle tool window only appears for macOS projects. For iOS/tvOS apps, use [TestFlight](testflight.md) for distribution.

## Resources

- [Sparkle Documentation](https://sparkle-project.org/documentation/)
- [Sparkle GitHub](https://github.com/sparkle-project/Sparkle)

## See Also

- [Releasing](releasing.md) - Building releases for distribution
- [Swift Packages](swift-packages.md) - SPM dependency management
