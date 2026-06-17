# Admin Guide

This guide explains how admins manage tasks, claims, submissions, and reviews in the Otter Harbor Claims dashboard.

## Admin access

Admins sign in with GitHub using an approved admin email address.

When signed in as an admin, the dashboard shows an **Admin tools** section.

Current admin emails are configured in the frontend code in the `ADMIN_EMAILS` list.

## Admin tools overview

Admins can:

* Add new tasks
* Update existing tasks by Display ID
* Review submitted tasks
* Approve completed tasks
* Undo submitted or approved tasks
* Clear expired claims

## Add or update a task

1. Open the dashboard.
2. Sign in as an admin.
3. In **Admin tools**, click **Add task**.
4. Fill in the task fields:

   * Display ID
   * Priority
   * Domain
   * Subdomain
   * Paper title
   * Venue / year
   * Sources
   * Task concept
   * Suggested Harbor steps
   * Verifier ideas
5. Click **Add task**.

If a task with the same Display ID already exists, the dashboard will ask whether you want to update it.

Adding or updating a task does not modify existing claims, submissions, or approvals.

## Review submitted tasks

Submitted tasks appear in the **Admin review queue**.

For each submitted task:

1. Check the paper title and task details.
2. Review the contributor email.
3. Review the submitted **Snorkel Submission ID**.
4. Verify that the submitted work is valid.
5. Click **Approve** if the work should be accepted.

After approval, the task status changes to **Approved**.

Approved tasks are no longer available to claim.

## Undo a submitted or approved task

Use **Undo submission** only when a task was submitted or approved by mistake.

This action changes the claim status to reopened and returns the task to the available pool.

Use this when:

* The wrong Submission ID was submitted.
* The submission should not have been approved.
* The task needs to be reassigned.
* The contributor should redo the task.

## Clear expired claims

Claims expire after 24 hours if they are not submitted.

Click **Clear expired claims** to release expired active claims.

This action only affects expired claims. It does not affect submitted or approved tasks.

## Contributor workflow admins should expect

Contributors will:

1. Sign in with GitHub.
2. Browse task cards.
3. Click **View details**.
4. Click **Claim task**.
5. Complete the task.
6. Paste their **Snorkel Submission ID**.
7. Click **Submit**.

Submitted tasks then appear in the admin review queue.
