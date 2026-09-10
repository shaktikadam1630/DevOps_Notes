# Basic Operations: Command-Line Essentials

This module covers the foundational commands you'll use constantly from here on: logging in and out, rebooting/shutting down, locating applications, navigating directories, understanding paths, exploring the filesystem, and working with links.

**Core commands introduced:** `cd`, `ls`, `cat`, `echo`, `man`, `mkdir`, `rmdir`

---

## 1. Logging In and Out

A text terminal prompts for a username (`login:`) and password. While typing your password, **nothing displays** — not even asterisks — to prevent others from seeing it.

### Remote Logins via SSH

Once logged in, you can connect to remote systems using **SSH (Secure SHell)**:

```bash
ssh student@remote-server.com
```

This connects securely to `remote-server.com` and opens a command-line session as `student` — authenticating either with a password or a cryptographic key (no password needed).

**Example:** A sysadmin managing 10 servers doesn't need to be physically near any of them — `ssh` into each one from a single laptop, run commands as if sitting right in front of it.

---

## 2. Rebooting and Shutting Down

The preferred method is the **`shutdown`** command — it warns logged-in users and blocks new logins before acting. **Always shut down properly**; improper shutdown risks data loss or system damage.

| Command | Action |
|---|---|
| `shutdown -h` | Halt (power off) — `halt`/`poweroff` are often aliases |
| `shutdown -r` | Reboot — `reboot` is an alias |

Both require **superuser (root)** access.

**Scheduled shutdown with a warning message:**
```bash
sudo shutdown -h 10:00 "Shutting down for scheduled maintenance."
```

**Example:** On a shared department server, scheduling `shutdown -h 22:00 "Maintenance tonight"` at 6pm gives everyone still logged in hours of advance warning, instead of their sessions dying without notice.

---

## 3. Locating Applications

Executables typically live in standard paths: `/bin`, `/usr/bin`, `/sbin`, `/usr/sbin`, sometimes `/opt`. Manually installed software often lands in `/usr/local/bin` / `/usr/local/sbin`, and users may keep personal binaries in `~/bin`.

> **usr-merge:** On modern systemd-based distros (Ubuntu 24.04, recent CentOS, openSUSE), `/bin` and `/sbin` are now symlinks into their `/usr` counterparts — so `/bin/diff` and `/usr/bin/diff` are literally the same file.

### Tools for Finding Commands

**`which`** — shows the full path based on your `$PATH`, confirming exactly which version will run:
```bash
$ which diff
/usr/bin/diff
```

**`whereis`** — broader: locates the binary, source, and man pages:
```bash
$ whereis diff
diff: /usr/bin/diff /usr/share/man/man1/diff.1.gz /usr/share/man/man1p/diff.1p.gz
```

**`type`** — a shell built-in that reveals what a command *actually is* (program, built-in, alias, or function):
```bash
$ type diff
diff is /usr/bin/diff

$ type ll
ll is aliased to 'ls -l --color=auto'
```

**Example:** If `ll` behaves unexpectedly, `type ll` immediately reveals it's not a real program but an alias for `ls -l --color=auto` — explaining behavior that `which` alone couldn't clarify, since `which` only finds real files on disk.

---

## 4. Accessing Directories

On login or opening a terminal, you typically land in your **home directory**. Confirm it with:
```bash
echo $HOME
```
`echo` prints text or a variable's value — used constantly in scripts.

> **Note:** How you opened the terminal matters — Activities search or `Ctrl+Alt+T` lands you in `$HOME`; right-click desktop → "Open in Terminal" often opens in `$HOME/Desktop` instead.

### Navigation Commands

| Command | Result |
|---|---|
| `pwd` | Print working directory (where you are now) |
| `cd ~` or `cd` | Go to home directory (`~` = tilde shortcut) |
| `cd ..` | Go to parent directory |
| `cd -` | Go to previous working directory |

### Managing a Directory Stack: pushd / popd

For moving between several directories and easily backtracking:

```bash
pushd /tmp              # go to /tmp, remember where you came from
pushd /usr/share/doc    # go there too, stack grows
dirs                    # show the full stack
popd                    # go back one step
popd                    # go back another step
```

**Example:** Jumping between `~`, `/tmp`, and `/usr/share/doc` while debugging a script, `pushd`/`popd` lets you retrace your steps exactly in reverse order — far less error-prone than remembering three separate `cd` commands to get back home.

---

## 5. Understanding Absolute and Relative Paths

**Absolute path** — starts at root (`/`) and follows the full tree. Always begins with `/`.

**Relative path** — starts from your *current* location, using shortcuts:
- `.` — current directory
- `..` — parent directory
- `~` — home directory

> Multiple slashes are collapsed: `////usr//bin` is treated identically to `/usr/bin`.

**Same destination, two ways** (starting from home directory):
```bash
cd /usr/bin           # absolute — shorter here
cd ../../usr/bin       # relative — longer in this case
```

**Which is better depends entirely on distance.** Close by → relative usually means less typing. Far away or uncertain → absolute is often shorter and less error-prone.

**Tip:** Lost in a complex directory structure? `pwd` always tells you exactly where you are.

---

## 6. Exploring the Filesystem

| Command | Result |
|---|---|
| `cd /` | Go to the root directory |
| `ls` | List contents of the current directory |
| `ls -a` | List **all** files, including hidden ones (start with `.`) |
| `tree` | Tree view of the filesystem |
| `tree -d` | Tree view, directories only |

> `tree` isn't installed by default on Ubuntu — install it with `sudo apt install tree` if you get "command not found."

**Example workflow:**
```bash
cd /usr/local/live     # absolute path from /usr
cd /usr                # back up
cd local/live           # same destination, relative path this time
cd /                    # jump to root
ls                       # list contents
ls -a                    # include hidden files
tree -d /               # directory-only tree from root
```

---

## 7. Hard & Soft Links

The **`ln`** utility creates links — additional ways to reference the same or related data.

![Hard Links vs. Soft (Symbolic) Links](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/hard-vs-soft-links.png?raw=true)

### Hard Links

```bash
ln file1 file2
```

`file2` is an **additional name for the exact same data** — both share the same **inode number** (the unique identifier for data on disk).

```bash
ls -li file1 file2
```
The inode number column matches for both, and the link count increments to 2.

**Key considerations:**
- **Data preservation** — the actual data isn't deleted until *every* hard link to it is removed
- **Use caution with editors** — some editors replace a file rather than editing in place, which can silently break the hard link relationship

### Soft (Symbolic) Links

```bash
ln -s file1 file3
```

`file3` gets its **own inode** and a distinct file type indicator (`l` at the start of the permissions string, plus a `->` pointing to the target). Unlike a hard link, it doesn't share data — it's a **pointer** to the original file's path.

**Key considerations:**
- **Cross-filesystem support** — symlinks can point across different partitions/disks/external media; hard links are confined to a single filesystem
- **Minimal overhead** — symlinks just store a text path, not a data copy
- **Flexibility** — repoint a symlink to a new location without touching the source
- **Dangling links** — since a symlink points to a *path*, not data directly, deleting/moving/unmounting the target leaves a broken ("dangling") link

**Example:** A `/usr/bin/python` symlink pointing to `/usr/bin/python3.12` lets you update Python versions system-wide just by repointing one symlink — no need to rename or move the actual interpreter binary itself.

---

## 8. Navigating the Directory History

`cd` remembers your **last** location — `cd -` returns to it. For deeper history, use `pushd`/`popd` (see Section 4) instead of plain `cd`, which builds a full list you can walk back through with `dirs`.

**Example:** Starting in `/usr/local`, running `pushd /tmp`, `pushd /boot`, `pushd /` builds a 4-deep stack. Running `popd` three times walks you back through `/boot`, `/tmp`, and finally `/usr/local` — in reverse order of how you arrived.

---

## Hands-On: Lab 7.2 — Locating Applications

**Task:** Find the location of the `ip` network utility using two different tools.

```bash
$ which ip
/usr/sbin/ip

$ whereis ip
ip: /usr/sbin/ip /usr/share/man/man7/ip.7.gz /usr/share/man/man8/ip.8.gz
```

**Why two different tools?** They answer different questions:
- **`which`** — searches only `$PATH`, reports the exact executable that would run. Best for confirming which binary is actually in use.
- **`whereis`** — searches standard system locations (beyond just `$PATH`), and finds more than the binary — matching man pages and source files too. This is why its output includes the man pages in addition to the binary path.

> **Note:** On many modern distros, `/sbin` is a symlink to `/usr/sbin`, so `/sbin/ip` and `/usr/sbin/ip` are the same file. On older/unmerged systems, `ip` may appear strictly under `/sbin`. Output may differ slightly by distro — the approach stays the same.

---

## The Full Picture

Everything in this module builds toward genuine command-line fluency: logging in securely (locally or via SSH), shutting down cleanly instead of yanking power, locating any command with `which`/`whereis`/`type`, and navigating the filesystem confidently using `pwd`, `cd`, absolute vs. relative paths, and the `pushd`/`popd` stack. Understanding hard vs. soft links rounds this out — knowing whether two filenames share the same data or one is just a pointer to the other is exactly the kind of detail that turns "why did deleting this file break something else" into an answerable question instead of a mystery.
