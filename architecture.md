---
title: Architecture
description: How the nbundle Platform, App Store, and apps work.
---

Understand how the nbundle Platform, App Store, & apps work. We'll be adding more information as we go along.

---

## Design & benefits

The nbundle application API (in `@nbundle/react` package) doesn't actually make any changes to Notion, instead, it dispatches messages to the nbundle App Store to handle the changes.

This comes with three huge benefits:

- It's nbundle's responsibility to maintain updates & compatibilities with Notion. When Notion UI changes, you don't need to make any changes to your app because it doesn't actually depend on the Notion UI, instead, the nbundle App Store will update itself on the users' devices and everything works as expected.

- Your app's size is a lot smaller because `@nbundle/react` is rather simple.

- There is no duplicated code & resources in the user's Notion because there is only the nbundle App Store that actually does the work.

---

## Permissions

Apps have read & write access to the user's current Notion workspace, databases, pages, & blocks.

The latest version of nbundle doesn't support granular permissions yet, but we'll be rolling out granular permissions as we go along. Granular permissions may limit apps to only read or write to certain parts of the user's Notion.
