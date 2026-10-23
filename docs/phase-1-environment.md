# Phase 1: Environment Setup

## Objective

Prepare an Ubuntu Server virtual machine for the Linux users, groups, and
permissions lab.

## Host and tools

- Host operating system: Windows 11
- Virtualization software: Oracle VirtualBox
- Code editor: Visual Studio Code
- Repository: `linux-users-groups-permissions`

## Virtual machine configuration

| Setting | Value |
|---|---|
| VM name | `linux-users-groups-permissions` |
| Guest operating system | Ubuntu Server |
| RAM | |
| CPUs | |
| Virtual disk | 25 GB, dynamically allocated |
| Network adapter | NAT |

## Installation choices

- Ubuntu release:
- Hostname: `ubuntu-lab`
- Initial administrator username: `labadmin`
- Storage: entire virtual disk
- OpenSSH server: installed

## Verification

Add the output or screenshots showing the Ubuntu release, hostname, memory,
processor count, and available disk space.

## Screenshots

Virtual machine configuration:

![Virtual machine configuration](/docs/screenshots/01-virtual-machine-settings.png)

First successful login:

![First successful login](/docs/screenshots/02-ubuntu-first-login.png)

System information from the terminal:

![System information from the terminal](/docs/screenshots/03-system-information.png)
