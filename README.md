<p align="center">
  <img src="https://res.cloudinary.com/dtptrqj5x/image/upload/v1780522658/banner_g8s9j8.webp" alt="CortenaOS" />
</p>

## Introduction

**CortenaOS** is an Android distribution focused on interaction quality, system consistency, performance stability, and long-term platform refinement.

Built on top of the Android Open Source Project (AOSP), **CortenaOS** combines a clean system experience with a modern interaction-driven design philosophy, powered by a growing ecosystem of custom platform components and Compose-based applications.

The project prioritizes fluidity, responsiveness, and cohesive system behavior over excessive customization or feature overload.

## Requirements

Before building **CortenaOS**, make sure your environment includes:

- A 64-bit x86 system
- A Linux distribution with glibc 2.17 or later
- At least 400 GB of free disk space

## Getting Started

```bash
# Install required packages
sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig

# Install Repo
sudo apt-get update
sudo apt-get install repo
repo version # Verify
```

## Repo Sync

```bash
# Create a directory for the repository
mkdir -p cortena
cd cortena

# Initialize the repository
repo init --partial-clone --no-use-superproject -b avalon -u https://github.com/cortenaos/manifest.git

# Sync sources
repo sync -c -j$(nproc --all)
```

## Setup Compiler Cache (Optional but recommended)

```bash
# Install ccache
sudo apt install ccache
echo "export USE_CCACHE=1" >> ~/.bashrc
echo "export CCACHE_EXEC=$(which ccache)" >> ~/.bashrc

# Source bash environment
bash

# Set cache size to 50GB
ccache -M 50G
```

## Build

```bash
# Set up the build environment
source build/envsetup.sh

# Choose a target
lunch cortena_<device_codename> bp4a userdebug

# Start compilation
m cortena -j$(nproc --all)
```

## Notes

```text
Current release: CortenaOS 1.0 "Avalon"
Based on Android 16 QPR2
```
