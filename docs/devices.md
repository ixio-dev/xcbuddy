# Device Management

XCBuddy provides device and simulator management through the Devices tool window.

## XCBuddy Devices Tool Window

Open via **View > Tool Windows > XCBuddy Devices**.

Lists available devices for running your app:
- iOS/tvOS/watchOS/visionOS Simulators
- Connected physical devices
- macOS (for Mac apps)

## Selecting a Device

Click a device to select it for **Run** commands. The selected device is remembered per project.

## Simulator Controls

For simulators, XCBuddy provides additional controls:

### Boot/Shutdown

- **Boot** - Start a simulator that's currently shut down
- **Shutdown** - Stop a running simulator

### Erase

Reset a simulator to factory state, removing all apps and data.

### Screenshots

Capture a screenshot of the simulator display. Screenshots are saved to your Desktop with the filename `XCBuddy-Screenshot-{timestamp}.png`.

### Screen Recording

Record video from the simulator:
1. Click **Record** to start
2. Perform actions in the simulator
3. Click **Stop** to end recording

Recordings are saved to your Desktop as `XCBuddy-Recording-{timestamp}.mov`.

## Platform Detection

XCBuddy automatically detects your project's target platform and filters the device list accordingly:
- **iOS projects** show iPhone/iPad simulators
- **macOS projects** show macOS option
- **tvOS projects** show Apple TV simulators
- **watchOS projects** show Apple Watch simulators

## Troubleshooting

### No Simulators Listed

Ensure Xcode is installed with simulator runtimes:
1. Open Xcode > Settings > Platforms
2. Install required simulator runtimes

### Simulator Won't Boot

Try erasing the simulator or creating a new one in Xcode.
