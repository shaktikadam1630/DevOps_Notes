# Preparing Your Computer for Linux

Before you start practicing Linux hands-on, you need a working Linux system of your own. Here's what you need to know, the main distributions worth choosing from, how installation media works, and the different ways you can get Linux running on your machine.

---

## What You'll Need

To practice Linux commands and get comfortable with the system, you need at least one Linux distribution installed and running — either on real hardware or inside a virtual machine.

There are hundreds of Linux distributions out there, but for someone starting out, it helps to focus on the three major families rather than trying to learn them all at once.

**Example:** It's the same idea as learning to drive using one car model first — the skills transfer to almost any other car, even if the dashboard looks slightly different.

---

## The Three Major Distribution Families

| Family | Good Beginner Pick | Package Manager | Best Known For |
|---|---|---|---|
| Red Hat | CentOS Stream / Fedora | dnf (RPM-based) | Enterprise production systems |
| SUSE | openSUSE LEAP | zypper (RPM-based) | Retail, strong system management (YaST) |
| Debian | Ubuntu LTS | apt (DPKG-based) | Beginners, cloud deployments, huge software repository |

**Recommendation for beginners:** Start with **Ubuntu LTS**. It has the largest community, the most tutorials and troubleshooting help online, and "just works" for most hardware out of the box.

**Official download locations:**
- [Ubuntu](http://www.ubuntu.com/)
- [Fedora](http://www.fedoraproject.org/)
- [Debian](http://www.debian.org/)
- [CentOS Stream](http://www.centos.org/)
- [openSUSE](http://www.opensuse.org/)
- [Linux Mint](http://www.linuxmint.com/)

**A note on switching later:** Once you get comfortable on one distribution, moving to another is fairly painless. The core concepts stay the same — the main differences are just package manager commands, software versions, and where certain files live.

---

## Understanding Installation Media

Every Linux distribution provides downloadable installation media, typically as an **ISO image** that gets written to a DVD or USB drive. This image can either install Linux permanently or let you run it temporarily without installing anything.

When downloading, you'll usually choose based on:

- **Architecture** — nearly all modern computers should use a **64-bit** image.
- **Package content:**
  - **Minimal image** — smaller download, pulls extra software during installation
  - **Full image** — larger download, includes most packages needed right away

**Example:** On slow home internet, a full image avoids a long download partway through installation. On a fast connection, a minimal image gets you started faster and you install only what you actually need afterward.

---

## Three Ways to Run Linux

![Three Ways to Run Linux](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/linux-installation-methods.png?raw=true)

### 1. Virtual Machine (Best Way to Start)

A **Virtual Machine (VM)** runs Linux inside your existing OS, as a guest system inside a **hypervisor**, while your main OS stays untouched as the host.

**Advantages:**
- Your host OS remains completely unchanged
- Mistakes inside the VM don't affect your main system
- Easy to reset or reinstall if something breaks
- Works fine even on locked-down work laptops

**Limitations:**
- Uses extra RAM and CPU
- Slightly slower than running Linux directly

**Tools to use:** Oracle VirtualBox (free, Windows/Linux/macOS) or VMware Player (free for Windows/Linux).

**Setup tip:** Point your hypervisor at the downloaded `.iso` file to create the VM, and allocate at least **20 GB** of disk space.

**Example:** If you're brand new to Linux, install VirtualBox on your current laptop and create a Ubuntu VM inside it — you can practice every command in this guide with zero risk to your actual computer.

### 2. Live USB/DVD (Good for Testing First)

Booting from a **Live USB or Live DVD** runs Linux directly from the removable drive — nothing gets installed.

**Advantages:**
- No changes made to your existing OS
- Great way to check hardware compatibility (Wi-Fi, sound, webcam) before committing
- Lets you explore the Linux desktop before deciding to install

**Limitations:**
- Slower to start each time (loads from scratch)
- Reduced performance compared to a real install
- Changes you make usually don't save after reboot

**Example:** Before wiping your laptop for a real install, boot from a Live USB first to confirm your Wi-Fi card actually works under Linux — saves you from an unpleasant surprise later.

### 3. Native Installation (Best Performance)

A **native installation** puts Linux directly onto your hardware, replacing or sitting alongside your current OS.

- **Dedicated install** — Linux replaces your existing OS entirely
- **Multi-boot install** — Linux installed alongside another OS; you pick which one to boot into

**Things to watch for:**
- Free up at least **20–30 GB** of disk space
- You may need to resize or create partitions — a tool like **gparted** helps with this
- Partitioning mistakes can cause data loss, so be careful
- **UEFI Secure Boot**, common on modern systems, may need to be adjusted in your BIOS/firmware settings first

**Example:** If you want Linux running at full speed for serious development work, set up a dual-boot with your existing OS — Linux for coding, your original OS for everything else, chosen at startup.

### Which One Should You Pick?

| Method | Best For |
|---|---|
| Virtual Machine | Just starting out, safest option |
| Live USB/DVD | Testing hardware before committing |
| Native Installation | Best performance, once you're comfortable |

---

## Checklist Before You Install

Go through this before installing, regardless of which method you choose:

- [ ] **Back up your data** — non-negotiable if you're doing a native install
- [ ] **Confirm you're downloading a 64-bit image** — correct for virtually all modern hardware
- [ ] **Boot into Live Mode first** to check that Wi-Fi and other peripherals work
- [ ] **Watch an install walkthrough** — search "How to install [distro name]" on any video platform before you start

**Example:** The most common regret beginners have is skipping the backup step — resizing partitions without backing up first can mean losing years of personal files if something goes wrong mid-install.

Once you've gone through this checklist, you're ready to install Linux and start practicing commands hands-on.
