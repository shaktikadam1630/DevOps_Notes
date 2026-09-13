# Working with Files and Directories

This module covers the day-to-day commands for viewing, creating, moving, renaming, and removing files and directories — plus customizing your command prompt.

---

## 1. Viewing Files

![Viewing Files: Which Tool, When](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/file-viewing-tools.png?raw=true)

| Command | Usage |
|---|---|
| `cat` | Views shorter files; no scroll-back |
| `tac` | Views a file backwards, starting from the last line (`tac` = `cat` reversed) |
| `less` | Pages through larger files — pauses per screen, supports scroll-back, search, navigation |
| `tail` | Prints the **last 10 lines** by default |
| `head` | Prints the **first 10 lines** by default |

**Inside `less`:** press `/` to search forward, `?` to search backward.

> **Note:** An older program `more` still exists but has fewer capabilities — hence the saying "less is more."

**Customizing line counts:**
```bash
head -20 file.txt      # first 20 lines
tail -20 file.txt      # last 20 lines (also works as tail -n 20)
```

**Line numbers:**
```bash
cat -n file.txt         # numbered lines with cat
less -N file.txt        # numbered lines with less
```

**Example:** Checking a 5,000-line log file, `cat` would flood your terminal instantly and scroll past before you could read anything — `less` is the right tool here, letting you page through and search for a specific error with `/error`.

---

## 2. touch

`touch` primarily updates a file's **access and modification timestamps** to the current time. But it has a second common use: **if the file doesn't exist, `touch` creates it empty** — a quick way to make placeholder files.

**Setting a specific timestamp:**
```bash
touch -t 12091600 myfile
```
Format: `[[CC]YY]MMDDhhmm[.ss]` — here, month 12, day 09, hour 16, minute 00 (year defaults to current year).

> **Note:** `ctime` (change time) can't be set directly — it always updates to the *real* current time whenever a file's metadata changes, including when `touch -t` modifies atime/mtime. So after this command, `ctime` reflects *now*, not December 9th.

**Example:** Creating a placeholder file for a script you'll write later: `touch deploy.sh` instantly creates an empty file you can open and edit — no need to open an editor just to save a blank file first.

---

## 3. Moving, Renaming, and Removing Files

### mv (move / rename)

Same command does both jobs — the destination determines which:

```bash
mv source destination
```

**Rename** (same directory):
```bash
mv notes.txt notes_old.txt
```

**Move** (different directory, name unchanged):
```bash
mv notes.txt /home/student/documents/
```

**Move and rename in one step:** just give a new name at the end of the destination path.

> **Trailing slash matters:** The destination directory must already exist. With a trailing `/` (`documents/`), `mv` errors if it doesn't exist. Without one (`documents`), `mv` instead **renames** `notes.txt` to a file literally called `documents` — rarely what you intended.

### rm (remove)

```bash
rm notes.txt
```

By default, `rm` only removes **files** — running it on a directory fails with "Is a directory." Add `-r` (recursive) to remove a directory and its contents, or `-rf` to also suppress prompts.

| Command | Usage |
|---|---|
| `mv` | Rename or move a file |
|
