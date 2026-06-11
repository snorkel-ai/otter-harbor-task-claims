# Otter Harbor Claims Admin Guide

This repo powers the Otter Harbor Claims dashboard.

The public dashboard reads from `tasks.json`. Admins manage claim status by editing `tasks.json` and using GitHub issues as the request/review log.

## Claim requests

When a contributor clicks **Request claim**, they create a GitHub issue labeled `claim-request`.

To approve a claim:

1. Open the claim request issue.
2. Confirm the task is still available in `tasks.json`.
3. Edit `tasks.json`.
4. Find the matching task.
5. Change:

```json
"status": "Available"
```

to:

```json
"status": "Claimed"
```

6. Commit the change to `main`.
7. Comment on the issue confirming the claim.
8. Close the claim request issue.

If the task is already claimed, comment that the task is no longer available and close the issue.

## Submitted tasks

When a contributor submits completed work, admins review the submission issue.

Use **Submitted** when the task has been handed in and is waiting for admin review.

In `tasks.json`, change:

```json
"status": "Claimed"
```

to:

```json
"status": "Submitted"
```

## Approve

Use **Approved** when the submitted Snorkel Submission ID actually used the example.

The task becomes approved and should not be claimed again.

In `tasks.json`, change:

```json
"status": "Submitted"
```

to:

```json
"status": "Approved"
```

Then comment on the submission issue and close it.

## Reopen

Use **Reopen** when the submitted Snorkel Submission ID did not use the example or the task needs another attempt.

In `tasks.json`, change the task status back to:

```json
"status": "Available"
```

Then comment on the issue explaining that the task has been reopened.

## Clear expired claims

There is no automatic 24-hour expiration yet.

To clear an expired claim manually:

1. Review tasks with `"status": "Claimed"`.
2. If the claim is stale, change the status back to:

```json
"status": "Available"
```

3. Comment on the original claim issue if appropriate.

## Recalibrate claims

Not needed in the GitHub version.

The dashboard reads directly from `tasks.json`, so updating `tasks.json` is the recalibration step.

## Reset all logs

Avoid resetting history.

In the GitHub version, issues and commits are the log. If a full reset is needed, update `tasks.json` statuses back to `Available`, but keep the GitHub issue/commit history intact.

## Status values

Use one of:

```text
Available
Claimed
Submitted
Approved
Blocked
```
