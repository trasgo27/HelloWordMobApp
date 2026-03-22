# Git Ignore Guide for Android Studio & Antigravity

This document summarizes the files and folders that should be excluded from version control (**Git**) to keep the repository clean and avoid conflicts.

---

## 1. Build & Temporary Folders
These are generated automatically every time you compile the project.
* **`/build/`**: Contains the compiled APKs and intermediate files. It is huge and unnecessary to track.
* **`.gradle/`**: The local cache for the Gradle build engine. It is specific to your machine's performance settings.

## 2. Local Environment Settings
These files contain paths and configurations unique to your computer (your D: drive setup).
* **`local.properties`**: Stores the path to your Android SDK. Sharing this would break the project for others with different drive letters.
* **`captures/`**: Screenshots and performance traces generated during debugging.

## 3. IDE Personalization (.idea folder)
While some files in `.idea` are useful, most are just "noise."
* **`workspace.xml`**: Remembers which files you have open and where your cursor is. It changes every few seconds.
* **`shelf/`**: Stores temporary "shelved" changes that aren't ready to be committed.
* **`dictionaries/`**: Your personal custom spell-check dictionary.

## 4. Operating System "Junk"
Hidden files created by Windows or macOS that have nothing to do with code.
* **`Thumbs.db`**: Windows thumbnail cache.
* **`.DS_Store`**: macOS folder metadata.

---

## 5. Sensitive Security Files
**NEVER** upload these to a public repository.
* **`*.jks` / `*.keystore`**: These are the digital keys used to sign your app. If stolen, someone else could update your app on the Play Store.
* **`google-services.json`**: Contains Firebase API keys. While usually safe, it's best practice to keep it private in professional teams.

> **Pro-Tip:** If you see a file in **Red** in Android Studio, it means it is not yet tracked. If it's in **Green**, it's staged. If it's in **Grey/White**, it's ignored or already committed.
