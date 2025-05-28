# GitLabs Setup for Windows
## Table of Contents

## Applications [Overview]
# Git Extensions



# Git Extensions
## Setup

## General Usage

## Issues

## Notes
<!-- DRAFT BEGIN -->
<!-- This is a random thing Chat explained to me earlier. It'll be useful evenually, but there's no good way to tie it in currently. -->
### Understanding Loose Git Objects and `git gc`

When working with Git, it's normal for the repository to accumulate **loose objects** over time. Here's what that means and how to handle it safely.

#### 🔍 What are Loose Objects?

- Git stores your project data (commits, files, trees) as **objects**.
- These objects can be stored in two ways:
  - **Loose Objects**: Individual files (one per object)
  - **Packed Objects**: Multiple objects grouped and compressed into a single file

Loose objects are created during normal Git operations such as:

- Running `git add`, `git commit`
- Performing merges, rebases, or stashes
- Making frequent small changes

Over time, having thousands of loose objects can slow down your Git operations.

#### ⚠️ Why This Message Appears

If you see:

> "This repository currently has approximately 5246 loose objects... To maintain optimal performance it is strongly recommended that you compress the database."

It means Git is suggesting you clean up and compress these objects to improve performance.

#### 🧹 What Does `git gc` Do?

Running `git gc` (short for "garbage collection"):

- Compresses loose objects into more efficient **packfiles**
- Cleans up unnecessary or unreachable objects
- Reduces disk usage
- Improves Git performance

#### ✅ Is It Safe?

Yes, running `git gc` is **safe** and **recommended**. It will **not delete your files** or lose your commits, as long as they are still reachable (e.g., referenced by branches or tags).

> 💡 If you're unsure, you can create a backup or clone the repository before running the command.

#### 🛠️ To Run the Cleanup

Open your terminal in the repo and run:

```bash
git gc
```

That's it! Your repository will be optimized and ready to go.
<!-- DRAFT END -->