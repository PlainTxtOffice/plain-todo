<!-- last_updated: 2026-11-22 -->

<!-- Authoring guidance: dev-docs/specs/README_SPEC.instructions.md -->
<!-- rumdl-disable MD033 MD041 -->
<p align="center">
  <img src="assets/icons/icon-github-readme.svg" alt="Plain Todo icon" width="96">
</p>
<h1 align="center">Plain Todo</h1>
<p align="center">
  Manage everyday tasks in readable todo.txt files on Android and iPhone.
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-Proprietary-blue" alt="License: Proprietary"></a>
  <a href="#android"><img src="https://img.shields.io/badge/platform-Android-3DDC84" alt="Platform: Android"></a>
  <a href="#windows-in-development"><img src="https://img.shields.io/badge/platform-Windows-0078D4" alt="Platform: Windows"></a>
  <a href="#download"><img src="https://img.shields.io/badge/platform-iOS-555555" alt="Platform: iOS"></a>
</p>
<!-- rumdl-enable MD033 MD041 -->

---

## About

**Development status:** The Android app is available on
[Google Play](https://play.google.com/store/apps/details?id=com.plaintxtoffice.plaintodo),
and the iPhone app on the
[App Store](https://apps.apple.com/app/id6837185055), where it is listed as
**Plain Todo Text**. The Windows version is still in development and has no
public download yet.

Plain Todo keeps your tasks in plain text that you can read and edit with other
todo.txt applications. Add priorities, projects, contexts, and due dates, then
complete tasks or move them into a separate archive.

<!-- rumdl-disable MD033 -->
<p align="center">
  <a href="assets/description.svg">
    <img src="assets/description.svg" alt="A todo.txt task line with its completion mark, priority, dates, description, and tags labeled" width="480">
  </a>
</p>
<!-- rumdl-enable MD033 -->

Your list stays in a file you control. Every app can keep it on the device or
connect directly to Dropbox. Android also opens a file you choose with the
system file picker, Windows works with a local file, and iPhone supports Files
and iCloud Drive. Each platform provides its own controls for working with the
same readable task format. There is no account to create and no advertising.

## Features

- **Plain-text tasks:** Keep one task per line, with optional priorities,
  dates, `+Project` tags, and `@context` tags.
- **Everyday editing:** Add, edit, complete, reopen, and delete tasks, with a
  confirmation before deletion.
- **Flexible organization:** Sort tasks by priority or due date, and group
  them by priority, due date, project, or context. Windows also sorts by
  project or context.
- **Archives and exports:** Move completed tasks to `done.txt` and export a
  plain-text copy of your task list.
- **Direct Dropbox access:** Connect each device to the same file, with
  server revision checks that stop conflicting saves.
- **Your own file (Android and iPhone):** Open an existing todo.txt through
  the system file picker, or keep the list in the app.
- **Task details and date editing (Android and iPhone):** View a task's dates
  and related tasks, and set due and threshold dates with calendar controls.
- **Notes (Windows, in development):** Keep optional task notes locally
  alongside the app's data.
- **iCloud Drive (iPhone):** Use the app's iCloud Drive location.
- **Recurring tasks (Windows, premium, in development):** Weekly, monthly, and
  quarterly routines kept in Markdown templates, for a paid premium edition.
  Paid-subscription activation is not currently available.

## App Screenshot

### Android

<!-- rumdl-disable MD033 -->
<p align="center">
  <a href="platform/android/assets/screenshots/android-task-list.png">
    <img src="platform/android/assets/screenshots/android-task-list.png" alt="Plain Todo on Android showing sample tasks sorted by priority" width="280">
  </a>
</p>
<!-- rumdl-enable MD033 -->

### Windows (in development)

<!-- rumdl-disable MD033 -->
<p align="center">
  <a href="platform/windows/assets/screenshots/windows-task-list.png">
    <img src="platform/windows/assets/screenshots/windows-task-list.png" alt="Plain Todo on Windows showing sample tasks and the task editor" width="640">
  </a>
</p>
<!-- rumdl-enable MD033 -->

## Download

| Platform | Download | Notes |
| --- | --- | --- |
| Android | [Google Play](https://play.google.com/store/apps/details?id=com.plaintxtoffice.plaintodo) | Requires Android 8.0 or later. |
| iPhone | [App Store](https://apps.apple.com/app/id6837185055) | Listed as **Plain Todo Text**. Version 1.3.0. Requires iOS 18.5 or later. |

A Windows download will be listed here when that app is released.

## User Manual

Read the [User Manual](docs/USER_MANUAL.md) for installation and initial setup,
daily tasks, platform-specific settings, file formats, shortcuts, and
troubleshooting.

## Feedback

Send bug reports and feature requests to
[support@plaintxtoffice.com](mailto:support@plaintxtoffice.com) or through the
[contact page](https://plaintxtoffice.com/contact/). In the Android app, open
**Settings** and tap **Send feedback**. In the iPhone app, open **Settings**
and tap **Send Feedback**, then choose **Report a bug**, **Request a
feature**, or **Open contact form**.

## Source and License

Plain Todo is proprietary software owned by Plain Text Office LLC. Source
code is maintained privately and is not published. See [LICENSE](LICENSE) for
the applicable terms. Third-party components retain their own licenses.
