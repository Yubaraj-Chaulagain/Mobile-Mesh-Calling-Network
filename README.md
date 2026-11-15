# MMCN – Mobile Mesh Calling Network

## Project target
MMCN is planned as an offline local-network voice communication app. **Any compatible Android phone should be selectable as the hotspot/router host**; the app must not be locked to one phone model.

## Included in this ZIP
- HTML offline/PWA app shell
- English, Nepali and Hindi language selector
- Local offline app shell and service worker
- Calling-mode interface placeholders
- Capacitor Android wrapper configuration
- GitHub Actions workflow for building an Android wrapper APK

## Important: current implementation status
This ZIP is a **starter/source package, not a finished calling app**. It does not yet provide real voice calls, Android hotspot control, device discovery, multi-router relay, automatic failover, or tested support for 30 devices. The calling controls in the UI are placeholders.

A normal web page cannot turn every Android phone into a router or configure hotspot/relay networking. That part needs native Android code and device-specific testing. Android phones differ in whether they can run a hotspot and join another Wi-Fi network at the same time, and hotspot client limits vary.

## Build the current Android wrapper
1. Install Node.js 20+ and Android Studio.
2. Run `npm install`.
3. Run `npx cap add android` (first time only).
4. Run `npx cap sync android`.
5. Run `npx cap open android` and build the APK in Android Studio.

The included GitHub Actions workflow can build the current wrapper after the project is pushed to GitHub. It does not add the missing calling/network functions.

## Required development stages for real MMCN calling
1. Native Android network permissions and router/host selection for compatible phones.
2. Local LAN device discovery and signaling server.
3. WebRTC audio for private calls.
4. Group audio, broadcast and push-to-talk.
5. Reconnection and supported relay/failover options.
6. Real-device tests, starting with a few phones before attempting a 30-device target.
