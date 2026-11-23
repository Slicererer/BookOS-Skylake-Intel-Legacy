# BookOS installation guide

> **Status: early development.** BookOS does not yet provide a working build script or installable image. These are the planned steps; wait for a tested release before trying to install it.

## First hardware target

The first compatibility target is Intel Sandy Bridge and Ivy Bridge laptops: AVX-capable processors that lack AVX2. Skylake-class hardware is also in scope. CPUs without AVX at all are outside the first phase.

## Planned build flow

BookOS is intended to be built locally from Google's public recovery image. The project will provide tools rather than redistribute Google's OS image or libraries.

When the port and build tools are ready, the expected flow is:

1. Use a Mac or Linux computer with Docker running, Python 3, and roughly 35 GB of free space.
2. Clone the BookOS repository and run its build script. The script will explain what it downloads and ask before downloading.
3. Let it obtain the public recovery image and the required build inputs, then create a USB image in the build output directory.
4. Review the finished image and its documented hardware support before installing.

The exact command, download sizes, and requirements will be added here after they match the BookOS build scripts.

## Planned USB use

Use a USB stick with at least 8 GB of capacity. Flash the generated image with a tool such as balenaEtcher or Rufus, or with `dd` on Linux/macOS. Select the USB device carefully: flashing overwrites its contents.

Boot the laptop from the USB using its firmware boot menu. The image is planned to offer a live session and an installer. Before installing to internal storage, confirm the installer’s target drive and back up files you need to keep.

## Compatibility reports

For early Sandy/Ivy Bridge trials, include the exact CPU model and the boot log when reporting a result. A successful boot on one model does not establish support for every laptop in that processor generation; Wi-Fi, graphics, audio, storage, and sleep can vary by machine.
