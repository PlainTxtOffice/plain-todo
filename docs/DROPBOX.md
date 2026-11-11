---
last_updated: 2026-11-11
version: 1.4.0
---

# Connect Plain Todo to Dropbox

Plain Todo can keep using a file on your device, or connect directly to
Dropbox. Direct Dropbox access checks the server's file revision when saving,
so competing edits are rejected instead of silently overwritten. This is
separate from opening a Dropbox file through your device's file picker or a
synced local folder.

| Platform | Status |
| --- | --- |
| Android | Released on Google Play. |
| Windows | In development; no public download yet. |
| iPhone | In development; no public download yet. |

The Windows and iPhone sections describe those apps as they are being built.

## Before connecting

You need a Dropbox account, internet access, and an existing UTF-8 task file
in Dropbox. Plain Todo includes its public app identity: users do not create
API keys, enter secrets, or copy authorization codes. Each user signs in to
their own Dropbox account and approves access. Sign-in uses OAuth with PKCE
and an automatic return to the app.

Use Dropbox file paths such as `/documents/todo/todo.txt` and
`/documents/todo/done.txt`, not paths on your device or sharing links. The
archive file can be created on first use; create its folder in Dropbox first.

## Connect on Android

1. Tap the gear button to open **Settings**, then tap **Dropbox Connection…**.
1. Enter the **Dropbox todo file** and **Dropbox archive file** paths. Both
   must start with `/` and they must be different files. The todo file must
   already exist in Dropbox.
1. Tap **Connect Dropbox…**, sign in, and approve access in your browser.
1. The browser returns to Plain Todo automatically. The app checks the task
   file and opens it straight away without uploading or moving the list you
   were using before.

To correct the paths after signing in, or to change the paths of an existing
connection, edit them and tap **Save File Paths**. You do not need to sign in
again. Closing the screen during sign-in leaves the previous connection as it
was.

The connection is encrypted with a key held in the Android Keystore and kept
in the app's private storage. It is not written into your task files or
exports. While connected, **Import a TODO.txt File** and
**Create New TODO.txt File** are unavailable, and **Settings** shows the
location as **Dropbox API**. Internet access is required; the app keeps no
offline queue or local copy of the Dropbox tasks.

### Save and reload on Android

Use **Settings > Reload Tasks** to fetch changes made elsewhere. Returning to
the app also reloads the list when nothing else is in progress. Every save
checks the revision that was loaded. When a save conflicts with a change from
another device, or its result is uncertain, the app reloads the latest list and
tells you the change was not saved. A failed edit stays in the edit screen and
a failed addition stays in the input box. After an uncertain save, review the
reloaded list before repeating the action: it may already have succeeded. A
save that never reached Dropbox, for example while offline, leaves the list
unchanged and can be tried again.

### Archive on Android

**Archive Now** and automatic archiving add the completed tasks to the Dropbox
archive file first, then remove them from the task file. If the archive file
does not exist yet, the app creates it. Each write checks its revision, but
the two writes are separate. If Dropbox rejects the archive write or never
receives it, neither file changes and you can archive again. If the app
reports that archiving may be partly complete, archiving stays blocked for the
rest of that session, even after reloading. Review both files, then close and
reopen the app, or reconnect, before archiving again.

### Disconnect on Android

Open **Settings > Dropbox Connection…** and tap
**Disconnect and use previous file**. The app removes the saved connection,
asks Dropbox to revoke its access, and returns to the file you used before.
The connection is removed even if the device is offline and the revocation
cannot be sent. Files in Dropbox are not deleted. Signing in again with a new
connection revokes the one it replaces. You can also remove the app's access
from the connected-apps page of your Dropbox account.

## Connect on Windows

1. Open **File > Dropbox Connection** in Plain Todo.
1. Enter the Dropbox paths for your existing todo file and archive, for example
   `/documents/todo/todo.txt` and `/documents/todo/done.txt`. These are Dropbox
   paths, not Windows paths or shared links. The two files must be different.
1. Choose **Connect Dropbox…** and approve access in your browser. The browser
   returns automatically. Plain Todo verifies the task file and saves the
   connection without uploading, merging, or moving your local tasks.
1. Restart Plain Todo. The window title and file label identify Dropbox mode.

If a path needs correcting after sign-in, edit it and choose **Save**; you do
not need to authorize again while the dialog stays open. **Cancel** leaves the
saved connection unchanged. Browser sign-in times out after three minutes.

The refresh token is stored in Windows Credential Manager. Settings contain
the app key, file paths, and a credential reference, not the token. A portable
copy moved to another Windows account or computer needs a new sign-in.

## Connect on iPhone

1. Open **Settings > Dropbox Connection…**.
1. Enter the Dropbox task and archive paths, using the same paths on every
   device that shares the list.
1. Tap **Connect Dropbox…**, sign in, and approve access in the system browser.
1. The browser returns automatically. The app validates and opens the existing
   remote task file immediately without uploading or moving your local list.

Use **Save File Paths** to correct paths after sign-in or change an existing
connection's paths. Cancelling sign-in leaves the previous connection intact.

The app stores the connection and refresh credential in a device-only Keychain
item. No app secret or generated access token is needed. A failed connection
attempt leaves your previous selection intact. Local-file and iCloud controls
are disabled while connected. Internet access is required; the app creates no
offline write queue or local mirror of Dropbox tasks.

Use **Settings > Reload Tasks** to fetch changes. Returning to the app also
reloads when no storage operation is running. Saves check the loaded revision
and never request automatic renaming. When a save conflicts with another
device's change, or its result is uncertain, the app reloads the latest list
automatically. Failed edits keep their text in the edit sheet, and failed
additions keep the input text. After an uncertain upload, review the reloaded
list before repeating the action: it may already have succeeded. A save that
never reached Dropbox, for example while offline, leaves the list unchanged and
can be retried without reloading.

**Archive Now** and automatic archiving append to the remote archive before
removing tasks from the remote task file. Each write checks its revision, but
the pair is not atomic. If Dropbox rejects the archive write or never receives
it, neither file changes and you can archive again. If the archive write has an
uncertain outcome or removing tasks fails after appending, archiving stays
blocked for that session even after reloading. Review both files before
reconnecting or restarting to retry.

Choose **Disconnect and use previous file** in the connection screen to remove
the saved authorization and return to your previous local or provider file.
The app also asks Dropbox to revoke that authorization; if the device is
offline, the connection is still removed. Connecting again with a new sign-in
revokes the replaced authorization the same way. Dropbox files remain
untouched. Keychain entries can survive uninstalling; disconnect before
removing the app to remove this record, or revoke access through Dropbox's
connected-app settings.

## Save and reload on Windows

Internet access is required to load and save Dropbox tasks. There is no local
task mirror or queue of offline writes. While a request is pending, Plain Todo
shows a progress window and prevents another task command from starting.

Choose **File > Reload Tasks** or press `Ctrl+R` to fetch other devices'
changes. This version does not automatically poll Dropbox. Saving checks the
revision even if you have not explicitly reloaded.

If someone changed the file, the save is rejected and Plain Todo offers to
reload. Declining keeps your editor changes visible. Accepting discards those
unsaved changes and loads the server version. There is no automatic merge or
force-overwrite option.

If the connection fails during a save, the upload may already have reached
Dropbox. Plain Todo requires a reload before another save attempt. Review the
reloaded tasks before repeating an action. A failed reload leaves the current
list and editor visible.

If Dropbox is unavailable when the program starts, choose **Retry**, open
**Dropbox Connection** to reconnect or return to local storage, or cancel
startup. A missing remote todo file is reported rather than recreated.

## Archive and notes on Windows

**Archive Completed** appends to the configured Dropbox archive before removing
completed tasks from the todo file. Both writes check server revisions, but
they are separate operations. An interrupted archive can leave tasks in both
files. Plain Todo reports this and blocks another archive attempt for that
session. Review both files, then restart before archiving again.

Task notes continue to use this Windows installation's existing notes storage.
They are not added to todo.txt or synchronized through the Dropbox connection.

## Disconnect on Windows

Open **File > Dropbox Connection** and choose **Disconnect and use local file**.
Restart to return to the previously configured local todo file. Disconnecting
does not copy, delete, or merge either file. The local file may contain
different tasks if it is not synchronized with the same Dropbox file.

Other apps can still edit synchronized copies of todo.txt. Unsynchronized edits
from those apps can still cause Dropbox conflicted copies; using direct access
in Plain Todo does not change how those other apps save.
