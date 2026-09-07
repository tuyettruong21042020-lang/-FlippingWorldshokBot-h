# Flipping Worlds Bot — Android prototype

This is a starter Android project for the Flipping Worlds screen-reading bot.

## What it currently does
- Uses MediaProjection to receive screen frames.
- Uses a lightweight pixel/colour detector (no cloud, no network).
- Sends taps through Android AccessibilityService.
- Has configurable Jump/Down coordinates.
- Contains hooks for Death -> first button, Menu -> coin/shop, and Start.

## Important
The supplied screenshots are examples, not a complete training dataset. The `Vision.java`
detector is intentionally a prototype and **will need live-frame tuning** for the exact
phone/browser/game viewport. It is not yet a guaranteed one-click autonomous bot.

## Build on Android
A Gradle-capable Android IDE can open this project. AndroidIDE is an example, but the
original AndroidIDE project is archived, so use a maintained fork/version if you choose it.

Requirements:
- Android SDK 35
- JDK 17
- Gradle/Android Gradle Plugin compatible with the project

Then build:
`./gradlew assembleDebug`

APK:
`app/build/outputs/apk/debug/app-debug.apk`

## First run
1. Install APK.
2. Open app.
3. Enable Accessibility for Flipping Worlds Bot.
4. Tap "Cấp quyền màn hình" and allow screen capture.
5. Open the game.
6. Calibrate Jump/Down coordinates if necessary.
7. Tap "BẮT ĐẦU BOT".

## Next tuning step
Record/capture several real gameplay frames for:
- clear road
- low obstacle
- high obstacle
- coin
- death screen
- menu
- shop

Then tune `Vision.java` so the detector uses those real frames rather than relying on
generic colour thresholds.
