# Plain Todo privacy policy — publication draft

<!-- Covers the iOS and Android apps. Add Windows and macOS behavior after
those ports are verified. -->

Updated November 22, 2026.

## Tasks and file access

Tasks and completed-task archives are stored in the app Documents folder or
files you choose through Files. The app stores settings, file-access bookmarks
and a provider display name locally. Task text can contain priorities, dates,
projects, contexts and other metadata.

## File providers and exports

Changes are written directly to the selected task and archive files. If you
choose iCloud Drive, Dropbox or another provider, that provider may upload,
synchronize or retain those files under its own policies. Export creates a copy
at the destination you choose. The app does not operate its own task server.

## Notifications

Notification permission is used for the app badge. This version has no remote
push-notification service. You can change permission in iOS Settings.

## Removing data

Delete tasks to remove their lines from the current task file. Archiving moves
completed tasks to done.txt rather than deleting them. You control archived and
exported files through Files. Switching to a local file does not delete the
previous external file. Deleting the app removes local app data and access
bookmarks, but external files, provider copies and device backups may remain.

## Developer services

This version contains no developer-run analytics, advertising or account
service. Device backups and services you choose, such as sharing destinations or
file providers, follow their own settings and policies.

## Plain Todo for Android

Plain Todo for Android keeps your tasks in a file in the app's private storage
or in a task file you choose with Android's file picker. Changes are written
straight to that file, and Export writes a plain-text copy to a destination you
choose. Android remembers that you allowed the app to read and write a file you
picked. The app has no accounts, advertising or analytics, and sends no
notifications.

The app uses internet access only for Dropbox. If you connect Dropbox in
Settings, the app sends task and archive contents directly to Dropbox over
HTTPS; they never pass through Plain Text Office servers. Your app key, file
paths and refresh credential are encrypted with an Android Keystore key in
private app storage, and are not saved in todo.txt or exported. Disconnect
removes that stored credential and asks Dropbox to revoke the authorization,
without deleting Dropbox files. You can also revoke the app's access in
Dropbox. Dropbox handles your files under its own policies.

If you choose Feedback, the app opens your email app with a draft addressed to
<feedback@plaintxtoffice.com> (<support@plaintxtoffice.com> in versions 1.0.2
and 1.0.3) that includes the app version, Android version and device model. You
can also open our contact page instead. Nothing is sent unless you send it. Task
contents are never included.

Android backup is turned on for this app. Files in app storage and your
settings can be included in Android backup and device-to-device transfer, if
you have those turned on. A saved Dropbox connection is not included.
Uninstalling the app removes its local files and the saved connection; files
you chose elsewhere and Dropbox files remain. If you share usage and
diagnostics with Google, Google may give us aggregated crash and performance
information.

## Apple diagnostics

We intend to use Apple-provided crash and performance information, when
available under your Apple diagnostic-sharing choices, only to troubleshoot
problems and improve reliability. App diagnostic logging should not
intentionally include document text, task contents, feed bodies, private
filenames, URLs, tokens or other private content. Apple controls its
system-generated reports; we cannot guarantee those reports contain no sensitive
information.

## Questions

Contact opens our website. We use the name, email address and message you
provide to respond to your request. Service providers may process this
correspondence for us. We retain it as needed to resolve the request or meet
legal obligations. Use the same contact form to request deletion.

Contact Plain Text Office: <https://plaintxtoffice.com/contact/>
