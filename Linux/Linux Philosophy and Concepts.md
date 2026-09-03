# Linux History

## The Beginning (1991)
Linus Torvalds was a student at the University of Helsinki, Finland, in 1991, when he started a personal project: writing his own operating system kernel. He also collected and developed the other essential ingredients required to build an entire operating system, with his kernel at its center. It wasn't long before this became known as the **Linux kernel**.

## Going Open Source (1992)
In 1992, Linux was re-licensed under the **General Public License (GPL)** by the **Free Software Foundation (FSF)**, which promotes freely available software. This enabled Linux to build a worldwide community of developers.

## The Rise of Distributions (Mid-1990s)
By combining the Linux kernel with other system components from the **GNU project**, developers around the world created complete systems called **Linux Distributions**, which first appeared in the mid-1990s.

## Full Timeline

![Linux History Timeline](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/linux-history-timeline.svg?raw=true)

| Year | Milestone | Details |
|------|-----------|---------|
| 1991 | Linux announced | Linus Torvalds releases the first version of the Linux kernel (v0.01) |
| 1992 | Linux becomes open source | Linus re-licenses Linux under the GNU General Public License |
| Mid 90s | First Linux distributions | Distros like Slackware and Debian created for free, open source computing |
| 1998 | Major companies adopt Linux | IBM, Oracle, and others begin investing in Linux, signaling enterprise legitimacy |
| 2003 | Red Hat Enterprise Linux (RHEL) | RHEL launches, marking the rise of commercial Linux distros for enterprise use |
| 2005 | Git created | Linus develops Git, a distributed version control system, to manage kernel development |
| 2007 | Android announced | Google unveils Android, based on the Linux kernel, bringing Linux to billions of mobile devices |
| 2011 | Linux turns 20 | The Linux Foundation celebrates two decades of innovation and collaboration |
| 2014 | Linux powers supercomputers | Linux runs 97% of the world's supercomputers |
| 2016 | Windows & Linux integration | Microsoft introduces the Windows Subsystem for Linux (WSL), starting a new era of cross-platform cooperation |
| 2017 | Linux dominates the cloud | Linux becomes the standard OS for cloud infrastructure, containers (Docker, Kubernetes), and DevOps platforms |
| 2020s | Embedded and AI growth | Linux expands into IoT, edge computing, and AI/ML environments, powering everything from smart devices to autonomous vehicles |
| 2024 | Linux dominates the world | Over 90% of public cloud workloads, and virtually all supercomputers and servers, now run Linux |

## Key Takeaways
- Linux began as one person's personal project, not a corporate initiative.
- The GPL license was the turning point that opened it up to global collaboration.
- Linux ≠ a full OS by itself — a distribution (kernel + GNU tools + more) is what makes it usable end-to-end.
- From a student's hobby project to running 90%+ of the cloud and nearly every supercomputer — Linux's growth is one of the great open-source success stories.

---

# Linux Philosophy Overview

Every successful project needs a guiding philosophy — a set of principles that shape how it grows and what it stands for. Linux is no exception, and understanding its philosophy is the key to understanding *why* Linux works the way it does.

## A Community, Not a Company

Unlike most operating systems, Linux was never built inside a corporate office. It's built by a network of developers scattered across the globe, collaborating over the internet, with Linus Torvalds guiding the project from the top. What's remarkable is who gets to contribute — there's no formal application, no gatekeeping committee. If you have the technical skill, the desire to contribute, and the willingness to work with others, you're already qualified.

## Born From UNIX, But Its Own Thing

To understand Linux, you have to go back to **1969**, when **UNIX** was born at AT&T Bell Labs. UNIX introduced ideas that were revolutionary at the time: a filesystem organized like a tree, the ability to run multiple programs at once, and support for multiple users on a single machine. Over the years, big companies took UNIX and built their own closed, paid versions of it — Oracle's Solaris, IBM's AIX, HP's HP-UX.

Then, in 1991, a university student named Linus Torvalds decided to write his own kernel. He didn't have access to UNIX's source code, and he didn't need it — instead, he studied *how* UNIX worked and built something new that followed the same spirit, but with completely independent code.

This is why the distinction matters: **Linux was inspired by UNIX, but Linux is not UNIX.** Think of UNIX as a handful of closed, expensive car brands — you buy exactly what the manufacturer gives you, take it or leave it. Linux, on the other hand, is like an open blueprint anyone can pick up, modify, rebuild, and give away for free. That's exactly why UNIX has only a few official versions, while Linux has hundreds of distributions — Ubuntu, Fedora, Debian, and more — each one a different take on the same open blueprint.

| | UNIX | Linux |
|---|---|---|
| **Origin** | AT&T, 1969 | Linus Torvalds, 1991 |
| **Code** | Closed, proprietary | Open source |
| **Cost** | Paid license | Free |
| **Owner** | A company (Oracle, IBM, HP) | No single owner — the community |
| **Versions** | A handful (Solaris, AIX, HP-UX) | Hundreds (Ubuntu, Fedora, Debian...) |
| **Customization** | Locked down by vendor | Fully open to modify |

## The Ideas That Define How Linux Works

Once Linux had its own identity, a handful of design principles emerged that still define it today.

The first is its **hierarchical filesystem**. Just like UNIX, everything in Linux lives in one giant tree structure, starting from a single root — written as `/` — with every file and folder branching outward from there.

The second, and arguably the most elegant idea in Linux, is that **almost everything is treated as a file**. Not just your documents and photos — but devices, running processes, even network connections are all represented as file-like objects. This means the same handful of commands you'd use to read a text file can also be used to talk to a hard drive or check a running process. It's one unified way of interacting with the entire system.

Third, Linux was built to be **multitasking and multiuser** from day one. It can juggle many processes running simultaneously, and it can host multiple people working on the same machine at the same time, each with their own private session and permissions.

And finally, Linux handles networking through **daemons** — quiet background processes, a concept it inherited straight from UNIX, that handle system and network tasks without ever needing you to intervene directly.

## Why This Philosophy Matters

Put it all together, and Linux's story is really a story about openness. A philosophy built on collaboration turned a student's personal project into an operating system with no single owner, shaped instead by anyone willing to contribute. And the technical principles it's built on — one filesystem tree, "everything is a file," multitasking for many users, and daemons quietly running the show — are the same ideas that still hold the entire system together more than three decades later.
# Linux Distributions

At the heart of every Linux system is the **Linux kernel** — the core piece of software that manages communication between hardware and applications. It controls resources like CPU, memory, and connected devices, and coordinates every program running on the system.

But the kernel alone isn't a usable operating system. A complete system needs libraries, utilities, applications, and often a graphical desktop on top of it. When all of these are bundled together with the kernel into one installable, maintainable package, that's called a **Linux distribution** (or "distro").

## What a Distribution Actually Packages

Each piece — the kernel, compiler, package manager, and so on — is usually built by a separate open source project with its own community. A distribution's real job is to bring all these independent pieces together, **test them for compatibility**, and make them easy to install and update.

![What Makes Up a Linux Distribution](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/linux-distribution-composition.png?raw=true)

| Component | Purpose | Examples |
|---|---|---|
| Compiler | Builds software from source code | GCC, Clang |
| Debugger | Tests and troubleshoots programs | gdb |
| Core Libraries | Shared code that applications depend on to run | glibc |
| Graphics System | Lets programs display visuals on screen | X11, Wayland |
| Desktop Environment | Defines how the system looks and feels | GNOME, KDE, Xfce |
| Package Manager | Installs, updates, and removes software | apt, dnf, zypper |

Most distributions also ship with a wide range of preinstalled applications — text editors, web browsers, system tools — so you can start working right after installation.

## Kernel Versions Differ Across Distributions

Distributions don't all ship the same kernel version, and they don't all adopt new kernels at the same pace:

- **RHEL 8** ships the older but very stable **4.18** kernel.
- **RHEL 9** is based on kernel **5.14**.
- **RHEL 10** is based on kernel **6.12**.
- **Fedora** and **openSUSE** adopt new kernel releases much faster, offering more cutting-edge features.
- Many distributions **backport** improvements — taking a feature from a newer kernel and adapting it to run on an older, more stable kernel base.

The full kernel archive (latest and historical releases) is maintained at **kernel.org**.

## Major Distribution Families

Because Linux is open source, there are hundreds of distributions. Grouping them by lineage makes them much easier to understand:

| Family | Package Manager | Popular Distributions |
|---|---|---|
| Debian-based | apt / dpkg | Debian, Ubuntu, Linux Mint, Kali Linux |
| Red Hat-based | dnf / rpm | RHEL, Fedora, CentOS Stream, AlmaLinux, Rocky Linux |
| SUSE-based | zypper / rpm | openSUSE, SUSE Linux Enterprise |
| Arch-based | pacman | Arch Linux, Manjaro |
| Independent | varies | Slackware, Gentoo |

## Commercial vs. Community Support

Large organizations — businesses, universities, government agencies — often rely on **commercially supported** distributions with professional support contracts and regular updates. The three most widely used are:

- **Red Hat Enterprise Linux (RHEL)** — maintained by Red Hat
- **SUSE Linux Enterprise** — maintained by SUSE
- **Ubuntu** — maintained by Canonical

For those who want RHEL compatibility without paying for support, free community alternatives exist. **CentOS** used to fill this role, but at the end of 2021 it was replaced by **CentOS Stream**, which tracks just ahead of RHEL's stable releases rather than mirroring them. In response, two community-driven distributions rose in popularity:

- **AlmaLinux**
- **Rocky Linux**

Both are designed to be **binary-compatible with RHEL** — software built for RHEL will generally run on them without modification.

Developers and educators often lean toward **Ubuntu** and **Fedora** for their up-to-date packages and ease of installation.

Whether commercial or community-driven, most distributions offer update services (security patches, bug fixes, performance improvements) along with documentation, forums, and wikis for support.

## Where to Explore Further
- **kernel.org** — the official Linux Kernel Archive
- **DistroWatch** — a comprehensive, regularly updated list of Linux distributions

---

# Linux Community

Imagine you're configuring a Linux file server and hit a problem you can't solve alone — the documentation doesn't help, and no one on your team knows the answer either. This is exactly where the **Linux community** becomes one of your most valuable resources.

The Linux ecosystem runs on **collaboration and shared knowledge**. Whether you're a system administrator, developer, or complete beginner, there are people who've already faced — and solved — the exact problem you're stuck on. You don't need to be a programmer to participate; community engagement is open to everyone.

## Ways to Get Involved

**Discussion Forums**
Sites like LinuxQuestions.org, Stack Overflow, and distribution-specific forums (Ubuntu, Fedora, etc.) are great places to ask questions and find solutions others have already worked out.

**Community Threads & Mailing Lists**
Following ongoing discussions and mailing lists/newsgroups keeps you in the loop on issues, fixes, and upcoming changes in projects you rely on.

**Local Linux User Groups (LUGs)**
In-person or virtual meetups where local enthusiasts share knowledge, host talks, and help each other troubleshoot — a great way to network beyond the screen.

**Chat Platforms**
Real-time community spaces such as IRC channels, Discord servers, and Matrix rooms exist for most major distributions and open source projects.

**Online Community Hubs**
**linux.com**, hosted by the Linux Foundation, is a great starting point — it draws over a million visitors a month and offers:
- News and community updates
- Discussion threads and user insights
- Free tutorials, best practices, and tips for all skill levels

**Collaborative Projects**
Contributing isn't limited to writing code — you can help with documentation, translations, bug reports, and testing.

**Community Events**
Conferences and meetups (Linux Foundation events, FOSDEM, and local LUG meetups) bring the community together in person to share knowledge and network.

## Learning Resources

Linux Foundation Education and other providers offer both self-paced and instructor-led courses — many free or low-cost — whether you're just starting out or working toward certification.

## Why It's Worth Participating

Engaging with the Linux community does more than solve your immediate problem — it builds your knowledge, grows your professional network, and contributes back to the open source movement that drives Linux forward.

---

# Linux Terminology — Quick Glossary

Before going deeper into Linux, it helps to have a solid grip on the core vocabulary. Here are the foundational terms you'll run into constantly:

| Term | What It Means | Examples |
|---|---|---|
| **Kernel** | The "brain" of the OS — controls hardware and connects it to applications | The Linux kernel (kernel.org) |
| **Distribution (Distro)** | A collection of programs combined with the kernel into a complete, usable OS | RHEL, Fedora, Ubuntu, Gentoo |
| **Boot Loader** | The program that loads and starts the operating system when the machine boots | GRUB, ISOLINUX |
| **Service / Daemon** | A program that runs continuously in the background to handle a specific task | httpd, nfsd, ntpd, ftpd, named |
| **Filesystem** | The method used to store and organize files on disk | ext3, ext4, FAT, XFS, Btrfs |
| **X Window System** | The standard toolkit and protocol used to build graphical interfaces on Linux | X11 |
| **Desktop Environment** | The graphical user interface layered on top of the OS | GNOME, KDE, Xfce, Fluxbox |
| **Command Line** | The text-based interface for typing and running commands directly | Terminal |
| **Shell** | The command-line interpreter that reads your input and tells the OS what to do | bash, tcsh, zsh |

Getting comfortable with this vocabulary makes it far easier to read documentation, follow tutorials, and communicate clearly with the rest of the Linux community.



