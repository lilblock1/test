# Bedrock Enhanced — external Android overlay v0.1.1

A standalone utility overlay for Minecraft Bedrock on Android. This does **not modify Minecraft**, hook the game, read memory, or implement gameplay cheats.

## Implemented in source

- Overlay permission screen and foreground service
- Draggable, persistent-position floating bubble, tap to open/close panel
- Adjustable custom crosshair (size and three colors), saved preference and touch pass-through
- Separate own-server / Realms UI profile setting
- Diagnostic display: Android battery percentage, display refresh rate, thermal status number (not Minecraft FPS)
- Minecraft launcher button
- Planned feature controls are disabled instead of falsely claiming implementation

## Build

GitHub Actions automatically builds `app:assembleDebug` on push. Download the `BedrockEnhanced-debug-apk` artifact from the completed workflow run. A debug APK is signed with a temporary CI key: builds from another runner may not install as an update.

## Test

1. Install the debug APK, open it, grant Display over other apps.
2. Start the overlay, then launch Minecraft using the button.
3. Drag the BE bubble, tap it, toggle the crosshair, and adjust size and color.
4. Verify Minecraft's taps still work outside the floating menu and crosshair window.
5. Stop the overlay in the companion app.

## Known limitations

Android may restrict overlays over certain full-screen apps. The crosshair is screen-centered, not the game's actual aim. Game FPS, flight, time/weather changes, ore highlighting, inventory tools, and other gameplay modifications require supported add-ons or game integrations; they are not implemented here. Realms cannot run arbitrary server plugins. Device testing not yet performed.
