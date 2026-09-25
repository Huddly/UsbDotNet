# Third-Party Notices

This is the Huddly fork of UsbDotNet. The original UsbDotNet project by Thomas Mittet is
licensed under the MIT License: https://github.com/tmittet/UsbDotNet. The C# code in this
repository remains under the MIT License (see `LICENSE`).

## libusb-1.0 (LGPL-2.1)

The `Huddly.UsbDotNet.LibUsbNative` package bundles precompiled binaries of
[libusb-1.0](https://libusb.info/), which is licensed under the GNU Lesser General Public
License, version 2.1 (LGPL-2.1). The full license text is provided in `LICENSE.libusb`
(packaged as `licenses/LICENSE.libusb`). Use of libusb does not imply endorsement by the
libusb project.

### Modified build (Windows x64 and arm64)

The `win-x64` and `win-arm64` binaries are a **modified** build of libusb-1.0, built from the
Huddly fork of libusb:

- Repository: https://github.com/Huddly/libusb
- Branch: `libusb-v1.0.30`
- Commit: `2ab95bfd7f9cdfb129e867e2240001772a0f3a8e`
- Reported libusb version: `1.0.30.62037`

The modifications are limited to the Windows (WinUSB) backend and are documented as change
notices in the fork's commit history, as required by LGPL-2.1 section 2(b). Compared to
upstream libusb 1.0.30, the fork opens the WinUSB device handle lazily on first use instead of
on `libusb_open`, and no longer clears endpoint data before an interface claim has succeeded.

The binaries were built from the commit above by the "Build libusb (Windows)" GitHub Actions
workflow in this repository (`.github/workflows/build_libusb_windows.yml`):
https://github.com/Huddly/UsbDotNet/actions/runs/36128292544

### Unmodified builds

All other bundled binaries (`win-x86`, `osx-x64`, `osx-arm64`, `maccatalyst-x64`,
`maccatalyst-arm64`) are unmodified builds of upstream libusb:
https://github.com/libusb/libusb. No binary is bundled for Linux; the system-installed
libusb-1.0 is used.

### Replacing the binaries

libusb is dynamically linked. The binaries are located in
`src/UsbDotNet.LibUsbNative/runtimes/<rid>/native/` in this repository and under
`runtimes/<rid>/native/` in the NuGet package. You may replace them with any compatible
libusb-1.0 build, as permitted by LGPL-2.1 section 6.

### Maintenance

Update the branch, commit, version and workflow run above on every release that changes the
bundled libusb binaries.
