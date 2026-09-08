# Shelter

Fork of `PeterCxy/Shelter`; `origin` is `https://github.com/rlsred/Shelter` on `master`.

## Build

- Initialize the vendored setup wizard library: `git submodule update --init --recursive`.
- Requires JDK 17 and Android SDK: compile/target SDK 35, build-tools 35.0.0.
- Local release check: `JAVA_HOME="$HOME/.local/android-build-tools/jdk-17" ANDROID_HOME="$HOME/.local/android-sdk" ./gradlew assembleRelease`.
- Do not claim a change is done without a successful `assembleRelease`.

## Signing and releases

- Preserve the existing release signing key; never generate or rotate it, commit it, or print its password.
- Expected signer certificate SHA-256: `113c941928f28f3a2c49165cdc00a5414ba417b3dc4d41a2565710d69bdbc30d`.
- `.github/workflows/release.yml` is manual-only. It signs the APK and publishes a GitHub Release from the supplied tag.
- Required GitHub **repository** secrets: `SHELTER_KEYSTORE_BASE64`, `SHELTER_STORE_PASSWORD`, `SHELTER_KEY_PASSWORD`.
- Verify a signed APK with `apksigner verify --verbose --print-certs <apk>` and inspect its manifest with `aapt dump badging <apk>`.

## Versioning

- `versionCode` is the first-parent commit count of `master`.
- `versionName` comes from `git describe --tags`; the release workflow creates its supplied tag before building.
