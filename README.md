# UsbDotNet

A modern, cross platform C# binding for [libusb](https://libusb.info/).  
Copyright (c) 2026 Thomas Mittet, project URL: https://github.com/tmittet/UsbDotNet/.  
Copyright (c) 2026 Huddly AS, fork URL: https://github.com/Huddly/UsbDotNet/.  

This is the Huddly fork of UsbDotNet. It bundles a modified build of libusb for Windows, see
[Third-Party libraries](#third-party-libraries) and `/THIRD-PARTY-NOTICES.md`.

NuGet packages: https://www.nuget.org/packages/Huddly.UsbDotNet/.  

## License

UsbDotNet is licensed under the MIT License (see `/LICENSE`). It dynamically links to libusb,
which is licensed under the LGPL-2.1. Precompiled [libusb](https://libusb.info/) binaries are
included in compliance with LGPL.

## Third-Party libraries

### libusb-1.0
- The libusb-1.0 library is bundled with this project for convenience
- libusb-1.0 is part of the [libusb project](https://github.com/libusb/) and is licensed under
  [LGPL-2.1](https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html)
- The `win-x64` and `win-arm64` binaries are a **modified build** of libusb-1.0, built from the
  [Huddly libusb fork](https://github.com/Huddly/libusb); the exact branch, commit and CI build
  are listed in `/THIRD-PARTY-NOTICES.md`
- All other bundled binaries are unmodified builds of upstream libusb
- Precompiled binaries are included in `/src/UsbDotNet.LibUsbNative/runtimes/`
- You may replace the binaries with any LGPL-compliant versions

### Licensing Notes
- The full LGPL-2.1 license text is provided in `/LICENSE.libusb`
- Third-party notices, including the source location of the modified libusb build, are
  provided in `/THIRD-PARTY-NOTICES.md`
- Use of libusb doesn’t imply endorsement from the libusb project
- If you modify or redistribute the libusb binaries, you must follow the
  [LGPL-2.1 terms](https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html)
