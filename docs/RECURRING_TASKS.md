---
last_updated: 2026-11-11
version: 1.0.1
---

# Premium recurring tasks on Windows

Recurring tasks help you manage routines that repeat every week, month, or
quarter. You define the tasks in Markdown files and track each period's
completion separately from your ordinary todo.txt list.

## Availability

Recurring tasks are in development for a premium edition of the Windows app,
which is itself still in development and has no public download yet. The
feature is not part of the Android app. Paid-subscription activation is not
currently available. This guide describes
the feature and how to use an edition with recurring-task access enabled; it
does not announce a purchasable release.

## What the feature offers

- Weekly, monthly, and quarterly task templates in readable Markdown files.
- A separate list of work for the current week, month, or quarter.
- Completion tracking for each period, with the option to reopen a task.
- Optional weekday headings to help organize weekly routines.
- Local completion records that survive closing and reopening the app.

Ordinary task editing, exports, and archives continue to use todo.txt and
done.txt. Recurring tasks do not add new records to those files.

## Set up your templates

Create a readable folder containing one or more of these files:

| Filename | Repeats during |
| --- | --- |
| `weekly.md` | Each Monday–Sunday week |
| `monthly.md` | Each calendar month |
| `quarterly.md` | Each calendar quarter, starting in January, April, July, or October |

You can omit files for schedules you do not use. Add named Markdown checkboxes
for the tasks you want to repeat. For example, `weekly.md` could contain:

```markdown
## Monday

- [ ] Review this week's priorities
- [ ] Plan meals

## Sunday

- [ ] Prepare for next week
```

Weekday headings are guidance: every weekly task is available throughout the
whole week. Completing a task early counts for that week; it does not appear
again on its suggested weekday. Recurring tasks have no automatic due dates.

Checked and unchecked boxes in a template both define future tasks. Use the
app's recurring-task list to record completion. Empty checkboxes without a task
name are ignored. Front matter does not determine the current week, month, or
quarter.

## Enable and use recurring tasks

These steps require an edition with recurring-task access enabled.

1. Open **Edit > Recurring Tasks...**.
1. Choose the template folder using **Browse...**.
1. Select **Enable recurring tasks**, then choose **Apply**.
1. Check a task to complete it for the current period. Uncheck it only when you
   want to reopen that occurrence.
1. Choose **Refresh** after editing your templates.

The list refreshes when opened, after **Apply** or **Refresh**, and every minute
while the dialog remains open. Completed tasks remain visible for the rest of
their period. New periods use your computer's local calendar.

Only the current period is generated. Missed periods are not filled in later,
and unfinished tasks from an earlier period do not carry into the current list.

## Edit templates without losing their identity

Avoid duplicate task names within the same schedule. To distinguish identical
names or keep a task's identity when renaming it, add an explicit ID:

```markdown
- [ ] Review plans <!-- recurring-id: quarterly-review -->
```

Keep that ID unchanged and unique within its schedule. Without an explicit ID,
renaming a task can create a separate task. Moving a weekly task to another
weekday heading keeps its identity; changing its weekly, monthly, or quarterly
schedule creates a new identity.

Existing tasks keep their title and suggested weekday until the next period.
Removing a template does not remove work already generated for the current
period. Switching template folders uses the same local task history, so it does
not create a separate library.

## Your records and limits

Completion history stays on the Windows installation. It does not follow your
todo.txt file to Dropbox, appear on your phone, or merge across computers.
Ordinary exports and archives do not include recurring tasks.

Turning off **Enable recurring tasks** stops generation and completion changes
without deleting saved records. If access becomes unavailable, saved tasks for
the current period remain readable. This version has no history browser.

If the app reports invalid templates or state, correct the reported problem
before trying again. Close the app before manually editing its stored state.
Deleting that state loses completion records and can recreate tasks you already
completed.

Return to the [User Manual](USER_MANUAL.md) for ordinary tasks, settings,
Dropbox connections, and troubleshooting.
