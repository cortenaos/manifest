<p align="center">
  <img src="https://res.cloudinary.com/dtptrqj5x/image/upload/v1777029971/banner_kjmi3r.webp" alt="CortenaOS" />
</p>

## Introduction

**CortenaOS** is an Android distribution focused on interaction quality, system consistency, performance stability, and long-term platform refinement.

Built on top of the Android Open Source Project (AOSP), **CortenaOS** combines a clean system experience with a modern interaction-driven design philosophy, powered by a growing ecosystem of custom platform components and Compose-based applications.

The project prioritizes fluidity, responsiveness, and cohesive system behavior over excessive customization or feature overload.

## Requirements

Before building **CortenaOS**, make sure your environment includes:

- A 64-bit x86 system
- At least 400 GB of free disk space
- A Linux distribution with glibc 2.17 or later
- Required software:
  - `Git`
  - `Repo`
  - `OpenJDK`
  - `Python 3`
  - `Make`

## Getting Started

```bash
# Initialize the repository
repo init -u https://github.com/cortenaos/manifest.git -b avalon

# Sync sources
repo sync -c -j$(nproc --all)
```

## Build

```bash
# Set up the build environment
. build/envsetup.sh

# Choose a target
lunch cortena_<device_codename>-bp4a-userdebug

# Start compilation
m cortena -j$(nproc --all)
```

## Notes

```text
Current release: CortenaOS 1.0 "Avalon"
Based on Android 16 QPR2
```
