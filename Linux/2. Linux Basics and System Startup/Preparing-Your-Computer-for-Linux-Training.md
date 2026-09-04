# Preparing Your Computer for Linux Training

Before diving into hands-on Linux work, you need a working Linux system to practice on. Here's what you need, which distributions this course uses, how to install Linux, and a final checklist before you begin.

---

## Software Requirements

This training is hands-on, so you'll need access to a working Linux system to practice commands and complete activities. If you already have Linux installed and running, you can skip the setup steps below — though the distribution background may still be useful.

To fully benefit from this course, you'll need at least one Linux distribution installed. This course doesn't attempt to cover every distribution — instead, it focuses on three primary distribution families, using selected examples from each for demonstrations and exercises.

**Example:** It's the same idea as learning to drive using one car model — the skills transfer to almost any other car, even if the dashboard looks slightly different.

---

## Linux Distributions Used in This Course

| Family | Reference Distro Used | Package Manager | Best Known For |
|---|---|---|---|
| Red Hat | CentOS Stream | dnf (RPM-based) | Enterprise production systems |
| SUSE | openSUSE LEAP | zypper (RPM-based) | Retail, strong system management (YaST) |
| Debian | Ubuntu LTS | apt (DPKG-based) | Beginners, cloud deployments, huge repository |

**Official download locations:**
- [Ubuntu](http://www.ubuntu.com/)
- [Fedora](http://www.fedoraproject.org/)
- [Debian](http://www.debian.org/)
- [CentOS Stream](http://www.centos.org/)
- [openSUSE](http://www.opensuse.org/)
- [Linux Mint](http://www.linuxmint.com/)

**Note on flexibility:** The material in this course is largely distribution-flexible — technical explanations, labs, and procedures work on almost all modern distributions. The main differences you'll notice are package management commands, software versions, and file locations. The desktop environment used throughout is **GNOME**, since it's the most widely used.

---

## Understanding Installation Media

Linux distributions provide downloadable installation media, typically as an **ISO image** written to a DVD or USB drive. This image can be used to install Linux permanently or run it temporarily without installing anything.

When downloading, you'll typically choose based on:

- **Architecture** — nearly all modern systems should use **64-bit** images.
- **Package content** — distros often offer:
  - **Minimal images** — smaller download, pulls additional software during installation
  - **Full images** — larger download, includes most packages needed right away

**Example:** Installing on slow home internet? A full image avoids a long download mid-installation. Setting up a cloud server with fast bandwidth? A minimal image gets you started faster.

---

## Recommended Installation Methods

![Three Ways to Run Linux](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/linux-installation-methods.png?raw=true)

### Virtual Machine (Recommended for Beginners)

A **Virtual Machine (VM)** runs Linux inside your existing OS, as a guest system inside a **hypervisor**, while your main OS remains the host.

- **Advantages:** host OS stays untouched, failures inside the VM don't affect your main system, easy to reset, fine with most corporate IT policies.
- **Limitations:** needs extra RAM/CPU, slightly slower than running natively.
- **Tools:** Oracle VirtualBox, VMware Player.
- Allocate **at least 20 GB** of disk space.

**Example:** A student experimenting with Linux for the first time uses VirtualBox on their Windows laptop — if they break something inside the VM, their actual laptop is unaffected.

### Live Media (For Testing)

Booting from a **Live USB or Live DVD** lets you run Linux directly from removable media, with no installation.

- **Advantages:** no changes to your existing OS, safe hardware compatibility testing (Wi-Fi, sound, webcam), explore before committing.
- **Limitations:** slower startup, reduced performance, changes usually don't persist after reboot.

**Example:** Before wiping your laptop to install Linux, booting into Live Mode first confirms your Wi-Fi card actually works under Linux.

### Native Installation (For Performance)

A **native installation** puts Linux directly onto your hardware — best performance, since there's no virtualization layer.

- **Dedicated installation** — Linux replaces your existing OS
- **Multi-boot installation** — Linux alongside another OS, chosen at boot time

**Important considerations:**
- Need **20–30 GB** of free disk space
- May need to resize/create partitions (tools like **gparted** help)
- Partitioning mistakes can cause **data loss**
- **UEFI Secure Boot** may need extra BIOS/firmware configuration

**Example:** A developer wanting Linux at full native speed for compiling large codebases sets up a dual-boot with Windows.

### Choosing the Best Option

| Method | Best For |
|---|---|
| Virtual Machine | Learning and experimentation |
| Live Media | Testing hardware compatibility |
| Native Installation | Best performance, more setup effort |

---

## Pre-Installation Checklist

- **Backup your data** — especially critical for a native installation.
- **Verify architecture** — 64-bit installs recommended for all modern hardware.
- **Check hardware compatibility** — boot into Live Mode first to confirm Wi-Fi and peripherals work.
- **Watch a demo** — search "How to install [Your Distro Name]" for a visual walkthrough.

**Example:** Skipping the backup step is the single most common regret — resizing partitions for a native install without backing up first can mean losing years of files if something goes wrong mid-process.

Completing this checklist ensures your system is ready for installation and that you can start course exercises with a stable, reliable environment.
