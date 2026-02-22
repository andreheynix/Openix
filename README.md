# Openix

Openix is a minimal Linux-based operating system designed primarily for
mobile devices.

It uses the Linux kernel directly with a custom userland. It does not
rely on the Android framework. It is built to be simple, modular, and
maintainable.

Mobile is the primary target. x86_64 builds are intended for development
and testing.

------------------------------------------------------------------------

## Project Structure

Openix/ ├── kernel/ Linux kernel source\
├── rootfs/ Base filesystem layout\
├── oxinit/ Custom init system\
├── oxd/ Core system daemon\
├── opkgx/ Package manager\
├── ui/ User interface components\
├── core/ Shared system components\
└── build/ Build scripts

------------------------------------------------------------------------

## Runtime Filesystem Layout

/boot\
/system\
/apps\
/data\
/config\
/dev\
/proc\
/sys\
/tmp

-   /system → Read-only system core\
-   /apps → Installed .opk packages\
-   /data → User data\
-   /config → Configuration files

------------------------------------------------------------------------

## Kernel

Openix uses a minimal Linux LTS configuration.

Targets: - ARM64 (primary) - x86_64 (secondary)

Enabled features include: - cgroups - namespaces - seccomp - DRM /
framebuffer - input device support

------------------------------------------------------------------------

## Init System (oxinit)

oxinit replaces traditional init systems.

Responsibilities: - Mounting virtual filesystems - Starting essential
services - Launching the Openix daemon

------------------------------------------------------------------------

## Core Daemon (oxd)

oxd manages: - Application lifecycle - Permissions - Power states -
Background limits - System events

------------------------------------------------------------------------

## Package System

Openix uses the .opk package format.

Packages are: - Signed - Installed under /apps - Isolated from the
system core

Package manager commands:

opkgx install \<package.opk\>\
opkgx remove `<package-id>`{=html}\
opkgx update

------------------------------------------------------------------------

## Status

Openix is in early development. Core system components and kernel
configuration are in progress.
