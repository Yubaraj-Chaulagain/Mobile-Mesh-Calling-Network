# MMCN – GitHub APK Build Package

## Upload to GitHub
1. Extract this ZIP.
2. Open your GitHub repository.
3. Upload all files and folders from this package to the repository root (not the ZIP itself).
4. Commit the files to the `main` branch.

## Build the APK
1. Open the repository's **Actions** tab.
2. Select **Build MMCN Android APK**.
3. Press **Run workflow** and select `main`.
4. Wait for the workflow to finish successfully.
5. Open the repository's **Releases** page.
6. Download `MMCN-debug.apk` from the release named `MMCN APK Build ...`.

The workflow publishes the APK as a GitHub Release asset, not only as an Actions artifact.

## Important status
This creates an installable Android debug wrapper around the current MMCN offline/PWA interface. It is NOT yet the finished offline calling app. Real WebRTC voice calling, Android hotspot/router control, device discovery, multi-router relay/failover and 30-device testing still need implementation.
