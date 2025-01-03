

---

# Guide to Run iOS App and Export `.app` File to Automation

This guide provides steps to:
1. Run the iOS app on a simulator or device.
2. Export the `.app` file (Debug or Release version).

---

## 1. Install Dependencies

This project uses **CocoaPods** for dependency management. Follow these steps to install the dependencies:

### Install CocoaPods (if not already installed):

```bash
sudo gem install cocoapods
```

### Navigate to the project directory and install dependencies:

```bash
cd my-demo-app-ios
pod install
```

This will generate a `.xcworkspace` file.

---

## 2. Run the App

### Open the Project in Xcode

Open the `.xcworkspace` file in Xcode:

```bash
open MyDemoApp.xcworkspace
```

### Select a Simulator or Device

1. In the toolbar at the top of Xcode, select a simulator or a connected iOS device from the dropdown menu.
   - Example: `iPhone 14 Pro (iOS 16.2)`.

### Build and Run the App

1. Click the **▶️ (Run)** button in the Xcode toolbar.
2. Xcode will build the project and launch the app on the selected simulator or device.

---

## 3. Export the `.app` File

### Select Build Configuration (Debug or Release)

1. In Xcode, go to the **Scheme Selector** in the toolbar.
2. Click **Edit Scheme**.
3. Under the **Run** section, select the **Info** tab.
4. Choose the desired build configuration:
   - **Debug**: For development and testing.
   - **Release**: For distribution or performance testing.

### Build the Project

1. Select a simulator or device from the dropdown menu in the Xcode toolbar.
2. Click **Product > Build** in the Xcode menu (or press `⌘ + B`).

### Locate the `.app` File

1. After building the project, the `.app` file will be located in the **Derived Data** folder.
2. To find the `.app` file:
   - Go to **Xcode > Preferences > Locations**.
   - Click the arrow next to the **Derived Data** path to open it in Finder.
   - Navigate to:
     ```
     DerivedData/MyDemoApp-<random-string>/Build/Products/
     ```
   - Look for the folder corresponding to the build configuration:
     - **Debug**: `Debug-iphonesimulator/` (for simulators) or `Debug-iphoneos/` (for physical devices).
     - **Release**: `Release-iphonesimulator/` (for simulators) or `Release-iphoneos/` (for physical devices).
   - Locate the `.app` file (e.g., `MyDemoApp.app`).

### Export the `.app` File

1. Copy the `.app` file to your desired location (e.g., Desktop):
   ```bash
   cp -r DerivedData/MyDemoApp-<random-string>/Build/Products/<Configuration>-iphonesimulator/MyDemoApp.app ~/Desktop/
   ```

   Replace `<Configuration>` with `Debug` or `Release`.

---

## Notes

- The **Release** version is required for App Store distribution or TestFlight testing.
- The **Debug** version is useful for development and debugging.

