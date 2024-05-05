# Steps to build apk file locally
- required jdk > 17 & < 20.

## 1. Install all dependencies
``` shell
npm install
```

## 1. Create prebuild
- Refer [official site](https://docs.expo.dev/workflow/prebuild/).
- ```prebuild``` generate actual React native project mainly android and ios project

```shell
npx expo prebuild --platform ios
npx expo prebuild --platform android
```

### 1.1. Clear existing native directories

- The `--clean` flag will delete any existing native directories before generating.
- When you re-run npx expo prebuild without the `--clean` flag, it layers the changes on top of your existing files.
- This is faster than re-generating from scratch, but it may not produce the same results in some cases.
- ex.:

```shell
npx expo prebuild --platform android --clean
```

## 2. Build apk
``` shell
cd android
./gradlew assembleRelease
```
- build output
``` shell
android/app/build/outputs/apk/release/app-release.apk
```
