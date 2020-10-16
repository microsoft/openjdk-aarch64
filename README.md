OpenJDK for Windows 10 ARM64
=====

This project only holds early access binaries of the initial port of OpenJDK for Windows on ARM64 devices and some accompanying documentation.

* See our [Contributing Guide](CONTRIBUTING.md).  **Please note** source code contributions are welcome through the [OpenJDK project](https://openjdk.java.net/contribute/). 
* Our [Code of Conduct](CODE_OF_CONDUCT.md).

*Early Access* binaries are available in the [releases](https://github.com/microsoft/openjdk-aarch64/releases) tab for experimentation.

## JDK Enhancement Proposal
This port is being proposed as a JEP to the OpenJDK project. The JEP can be found at [https://openjdk.java.net/jeps/388](https://openjdk.java.net/jeps/388).

This JEP is being tracked under the [JDK-8248496](https://bugs.openjdk.java.net/browse/JDK-8248496) work item.

## Source Code
All source code changes to OpenJDK, required to implement this port, are being tracked under the [JDK-8248238 Implementation of JEP: Windows AArch64 Support](https://bugs.openjdk.java.net/browse/JDK-8248238).

The source code is available through Webrevs in the OpenJDK project.

- Webrev P1: http://cr.openjdk.java.net/~burban/winarm64_p1_llp64/
- Webrev P2: http://cr.openjdk.java.net/~burban/winarm64_p2_new-target/

## Supported Windows Versions

- Windows 10
- Windows Server 2016

## Supported Garbage Collectors
- Serial GC
- Parallel GC
- G1 GC (temporary workaround until the [MSVC bug](https://developercommunity.visualstudio.com/content/problem/1079221/arm64-bad-code-generation-around-signed-char-arith.html) has been fixed)
- Z GC
- Shenandoah GC

## FAQ

### Is this build TCK'ed?

Early Access binaries will not be TCK'ed. 

### Where can I test this build?

We have uploaded our Arm64 test systems information [here](https://github.com/microsoft/openjdk-aarch64/blob/master/Arm64_systems.md). You can find retail laptops with ARM64 and Windows, such as HP Enxy x2, Asus NovaGo, and the Microsoft Surface Pro X.

For additional information, please visit [Works on Arm](https://www.worksonarm.com/?_ga=2.204290832.1614868344.1591633956-103015898.1581534333) website.

### What Java tools run on this build?

The following tools have been tested, though not extensively, and did not show any immediate issues:

- Apache Maven
- Apache Ant
- Gradle
- Visual Studio Code Java Extension Pack (note: must change configurations to use Parallel GC)

## Build dependencies

We rely on VS 2019 and the following individual components:
-	MSVC v142 - VS 2019 C++ ARM64 build tools (v14.26)
-	MSVC v142 - VS 2019 C++ x64/x86 build tools (v14.26)
-	C++ ATL for latest v142 build tools (ARM64)
-	C++ ATL for latest v142 build tools (x86 & x64)
-	C++ MFC for latest v142 build tools (ARM64)
-	C++ MFC for latest v142 build tools (x86 & x64)
-	Windows 10 SDK (10.0.18362.0)

Other dependencies are:
-	Cygwin
-	Java 16 for boot and build JDK 

We recommend using the devkit, which can be created like so:
```console
$ make/devkit/createWindowsDevkit2019.sh
```

More infos about devkit usage can be found here: https://github.com/openjdk/jdk/blob/master/doc/building.md#cross-compiling-the-easy-way-with-openjdk-devkits
### Building from github.com/openjdk/jdk.git

Platform support has been merged recently, but there is still a [build system issue](https://github.com/openjdk/jdk/pull/212#issuecomment-695024586). You'll need to apply this patch to make the build work: https://gist.github.com/lewurm/c099a4b5fcd8a182510cbdeebcb41f77

## Feedback

Please send email to [aarch64-port-dev@openjdk.java.net](http://mail.openjdk.java.net/mailman/listinfo/aarch64-port-dev). 

Microsoft is committed to working on an *upstream first* approach, so please reach out through the mailing list above. If you do want to contact the Microsoft team directly, please email openjdk-aarch64@microsoft.com.
