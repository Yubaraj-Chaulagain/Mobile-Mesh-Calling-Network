# MMCN – Mobile Mesh Calling Network

**Developer:** Yubaraj Chaulagain  
**Platforms:** Offline-first HTML/PWA + Capacitor Android wrapper  
**Languages in the starter UI:** English, नेपाली, हिन्दी

## Included in this package
- Responsive MMCN dashboard UI
- Language selector with local preference storage
- Offline app shell and service worker
- Calling-mode entry points: Private, Group, Broadcast, Walkie-Talkie
- Capacitor Android configuration
- GitHub Actions workflow at `.github/workflows/build-apk.yml` to build a debug APK

## Important: current implementation status
This package is a **buildable project foundation, not a completed offline calling/mesh system**. The current buttons are interface placeholders. It does not yet transmit voice, discover nearby phones, control Android hotspots, relay traffic between hotspots, or provide router failover. The APK workflow only packages the current web app into an Android shell; it does not add those missing networking features.

A real offline voice network needs Android-native networking and audio/signaling work. Android phones differ in whether hotspot and Wi-Fi client modes can run together, whether hotspot clients can communicate with one another, and how many clients are allowed. A 30-device target and multi-router failover must be tested on the actual phone models and cannot be guaranteed by this starter.

## Build the Android APK locally
Requirements: Node.js 20+, Java 17, Android SDK.

```bash
npm install
npx cap add android   # first build only
npx cap sync android
npx cap open android
```

Build a debug APK from the Android project:

```bash
cd android
./gradlew assembleDebug
```

APK output: `android/app/build/outputs/apk/debug/app-debug.apk`.

## Build with GitHub Actions
1. Upload this project to a GitHub repository.
2. Push the files to the `main` branch.
3. Open **Actions → Build MMCN Android APK → Run workflow** (or push a change under `www/`).
4. Download the `MMCN-debug-apk` artifact from the completed workflow run.

## Planned engineering phases
1. Verify local connectivity between devices on one phone hotspot.
2. Implement Android-native device discovery and a local signaling service.
3. Implement WebRTC audio for private calls, then group calls.
4. Add broadcast and push-to-talk behavior.
5. Evaluate supported phone-to-phone relay options and test reconnect/failover.
6. Load-test the intended device count on the target hardware.
