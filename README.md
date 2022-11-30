OpenJDK for Windows on ARM64
=====

This project holds the documentation for Microsoft's port of OpenJDK for Windows on ARM64 devices.

* See our [Contributing Guide](CONTRIBUTING.md).  **Please note** source code contributions are welcome through the [OpenJDK project](https://openjdk.java.net/contribute/).
* Our [Code of Conduct](CODE_OF_CONDUCT.md).

### The Microsoft Build of OpenJDK

General Access (GA) binaries can be downloaded from [the official release page](https://docs.microsoft.com/en-us/java/openjdk/download).

A number of older builds can be found under the [releases](https://github.com/microsoft/openjdk-aarch64/releases) tab.

### JDK Enhancement Proposal
The JEP can be found at [https://openjdk.java.net/jeps/388](https://openjdk.java.net/jeps/388).

The work was tracked under the [JDK-8248496](https://bugs.openjdk.java.net/browse/JDK-8248496) item and has been delivered in OpenJDK 16. The work was later backported to JDK 11.

### Source Code
Source code changes required to implement this port were tracked under [JDK-8248238](https://bugs.openjdk.java.net/browse/JDK-8248238).

The port was merged into OpenJDK 16 and since then has been part of the [OpenJDK mainline](https://github.com/openjdk/jdk). Like previously stated, the port was later backported to JDK 11.


### Supported Windows Versions
- Windows 10/11
- Windows Server 2016

### Supported Garbage Collectors
- Serial GC
- Parallel GC
- G1 GC
- ZGC
- Shenandoah GC

### FAQ

#### Are Microsoft's builds TCK'ed?

Yes.

#### Where can I test this build?

We have uploaded our ARM64 test systems information [here](https://github.com/microsoft/openjdk-aarch64/blob/master/Arm64_systems.md). You can find retail laptops with ARM64 and Windows, such as HP Enxy x2, Asus NovaGo, and the Microsoft Surface Pro X.

For additional information, please visit the [Works on Arm](https://www.worksonarm.com/?_ga=2.204290832.1614868344.1591633956-103015898.1581534333) website.

#### What Java tools run on this build?

The following tools have been tested, though not extensively, and did not show any immediate issues:

- Apache Maven
- Apache Ant
- Gradle
- Visual Studio Code Java Extension Pack

## Building the JDK for Windows ARM64

The native Visual Studio build toolset for ARM64 has become available in Visual Studio 2022 17.3 Preview2 (as of June 2022). To find out more information on how to setup this version of Visual Studio please visit the [Microsoft Docs](https://docs.microsoft.com/en-us/visualstudio/install/visual-studio-on-arm-devices?view=vs-2022). For those not using the native Visual Studio build toolset for ARM64, the JDK can be cross-compiled for Windows ARM64. This means that the build happens on an x64/x86 machine, but the resulting binaries run on ARM64.

### Dependencies

We recommend using the latest version of Visual Studio available. At a minimum VS 2019 (16.8) is required. The following individual components are needed (with example versions):
-	MSVC v143 - VS 2022 C++ ARM64 build tools (Latest)
-	MSVC v143 - VS 2022 C++ x64/x86 build tools (Latest)
-	C++ ATL for latest v143 build tools (ARM64)
-	C++ ATL for latest v143 build tools (x86 & x64)
-	C++ MFC for latest v143 build tools (ARM64)
-	C++ MFC for latest v143 build tools (x86 & x64)
-	Windows 10 SDK (10.0.18362.0)

Other dependencies are:
-	Cygwin
-	Boot and build JDK:
    - To build JDK 11 for ARM64, x86/x64 JDK 11 binaries are needed.
    - To build the latest JDK for ARM64, x86/x64 binaries of one of the latest 3 JDK versions are needed. At the time of writing (June 2022) one can use either JDK 17, 18 or 19.
    - These binaries can be obtained from any vendor.

### Building the latest JDK

Sources are available at https://github.com/openjdk/jdk.

The usual build process can be used with the following configure arguments:

```shell
$ bash configure
    --openjdk-target=aarch64-unknown-cygwin
    --with-boot-jdk=<path-to-x86_64-JDK>
```
### Building JDK 11

Windows-ARM64 support is available as part of the official OpenJDK 11 Updates project starting from 11.0.14.

Sources are available at https://github.com/openjdk/jdk11u.

An example minimal configuration:

```shell
$ bash configure \
    --openjdk-target=aarch64-unknown-cygwin
    --with-boot-jdk=<path-to-x86_64-JDK>
```

Note that:
* Since we are cross-compiling, the build must happen on a `x86_64` machine with the `--openjdk-target=aarch64-unknown-cygwin` specified as shown above.
* If you want to enable Shenandoah GC in this build, you have to explicitly enable it via: `--with-jvm-features=shenandoahgc`.

## Feedback

- Microsoft is committed to working on an *upstream first* approach, so for port related questions, please reach out through the [aarch64-port-dev@openjdk.java.net](http://mail.openjdk.java.net/mailman/listinfo/aarch64-port-dev) mailing list. If you do want to contact the Microsoft team directly, please email openjdk-aarch64@microsoft.com

- To provide feedback or to report issues regarding Microsoft's Build of OpenJDK, please reach out to us @[github.com/microsoft/OpenJDK](https://github.com/microsoft/OpenJDK). Thank you.
