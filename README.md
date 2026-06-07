# MaestroDeck (Android)

The MaestroDeck mobile app for Android, native Kotlin. For now it is a minimal
app showing a single centered text, used to exercise the
[`BlueShork/maestro-action`](https://github.com/BlueShork/maestro-action) CI
workflow on Android.

## Project

A minimal single-Activity app (no AndroidX, plain `android.app.Activity` with a
centered `TextView`). Build the debug APK with Gradle:

```bash
gradle assembleDebug
# -> app/build/outputs/apk/debug/app-debug.apk
```

- Application id: `com.maestrodeck.mobile`
- Source: `app/src/main/`
- Maestro flows: `.maestro/`

## CI

On every push, `.github/workflows/ci.yml`:

1. Builds the debug APK with Gradle 8.7 (AGP 8.5).
2. Runs the Maestro flows on MaestroDeck Cloud via `BlueShork/maestro-action@v1`.

Requires a repository secret `MAESTRO_API_KEY` (a MaestroDeck Cloud API key).
