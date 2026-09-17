# Shelter — Lane's fork

A maintained fork of [PeterCxy/Shelter](https://github.com/PeterCxy/Shelter), which uses Android Work Profiles to isolate apps from the personal profile.

## Added features

- Install CA certificates in the work profile.
- Opt-in file picking between personal and work profiles through Android system pickers, including the Photo Picker, `ACTION_GET_CONTENT`, and `ACTION_OPEN_DOCUMENT`.

File sharing is disabled by default and only grants access to files explicitly selected by the user.

## Downloads and releases

Download signed APKs from [Releases](https://github.com/rlsred/Shelter/releases).

GitHub Actions builds, signs, and publishes releases from a supplied tag. Fork APKs use a different signing key from upstream and F-Droid builds, so Android requires uninstalling the existing Shelter app before switching between them.

## Build

```sh
git submodule update --init --recursive
JAVA_HOME="$HOME/.local/android-build-tools/jdk-17" \
ANDROID_HOME="$HOME/.local/android-sdk" \
./gradlew assembleRelease
```

## Upstream

- [Upstream project](https://github.com/PeterCxy/Shelter)
- [Cross-profile file-picking PR](https://github.com/PeterCxy/Shelter/pull/321)
