# What To Eat

A small Android app for when you **don’t know what to eat**. You keep a personal list of restaurants; the app suggests the next place in a fair rotation, tracks how many times you’ve been, and lets you shuffle a pick if you’re not feeling it yet.

## Features

- **Pick for me** — One big action suggests the next place (oldest visit → newest). Your list stays off this screen so picks feel like a surprise.
- **My list** — Add, edit, or delete places (name + optional notes). Order reflects visit recency.
- **Eating it!** — Marks today’s visit and sends the place to the back of the rotation.
- **Not now** — Moves the suggestion deeper in the list (random slot about 25–50% down) so you see other places first. Disabled when you only have one entry.
- **Visit counter** — Each “Eating it!” increments a per-place tally, shown on the list and on the suggestion sheet.

## Tech stack

- **Kotlin**, **Jetpack Compose**, **Material 3**
- **Room** (SQLite) + **KSP**
- **Navigation Compose** (drawer: Pick for me / My list)
- Min SDK **26**, targets current Android / API **35** (see `app/build.gradle.kts`)

## Prerequisites

- [Android Studio](https://developer.android.com/studio) (recommended) or Android SDK + JDK **17** (JDK 21 for Gradle is usually fine too)
- Accept SDK licenses and install a recent **Android SDK Platform** matching `compileSdk`

## Open & run

1. Clone the repo and open the **`what-to-eat`** folder in Android Studio.
2. Let **Gradle sync** finish.
3. Choose a device (emulator or phone with USB debugging) and press **Run**.

## Build a shareable APK

- **Debug (quick):** **Build → Build APK(s)**  
  Output is typically:  
  `app/build/outputs/apk/debug/app-debug.apk`

- **Release (for friends / outside your machine):**  
  **Build → Generate Signed App Bundle or APK → APK**, then follow the keystore steps.  
  Share the generated **release APK**; recipients install it from Files/Downloads (may need “Install unknown apps” for that source).

## Command-line ADB (PowerShell)

Invoke `adb` with the call operator:

```powershell
& "$env:LOCALAPPDATA\Android\Sdk\platform-tools\adb.exe" devices
```

Install a debug build after assembling:

```powershell
& "$env:LOCALAPPDATA\Android\Sdk\platform-tools\adb.exe" install -r app\build\outputs\apk\debug\app-debug.apk
```

Adjust the SDK path if yours differs (**Android Studio → Settings → Android SDK → Android SDK Location**).

## Brand & theme

UI colors are built around **#203731** (green) and **#FFB612** (gold), with teal/coral accents in the Material 3 color scheme.

## License

Add a `LICENSE` file if you want others to know how they may use the project (e.g. MIT).

---

Made for deciding dinner without the endless group chat.
