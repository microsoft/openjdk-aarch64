OpenJDK for Windows 10 ARM64
=====

This project holds binaries and documentation for Microsoft's port of OpenJDK for Windows on Arm64 devices, as well as Arm64 binaries built by Microsoft for all operating systems supported by the OpenJDK project.

* See our [Contributing Guide](CONTRIBUTING.md).  **Please note** source code contributions are welcome through the [OpenJDK project](https://openjdk.java.net/contribute/). 
* Our [Code of Conduct](CODE_OF_CONDUCT.md).

General Access (GA) binaries are available under the [releases](https://github.com/microsoft/openjdk-aarch64/releases) tab.

### JDK Enhancement Proposal
The JEP can be found at [https://openjdk.java.net/jeps/388](https://openjdk.java.net/jeps/388).

This JEP was tracked under the [JDK-8248496](https://bugs.openjdk.java.net/browse/JDK-8248496) work item and they have been delivered in OpenJDK JDK16.

### Source Code
All source code changes to OpenJDK, that were required to implement this port, were being tracked under [JDK-8248238 Implementation of JEP: Windows AArch64 Support](https://bugs.openjdk.java.net/browse/JDK-8248238).

The source code is merged into JDK 16 and is now a part of the [OpenJDK project](https://github.com/openjdk/jdk). 
Here's a [link to the source code for Microsoft's GA build of OpenJDK 16.0.2](https://download.visualstudio.microsoft.com/download/pr/b0e444d2-a821-428a-b1b2-b751a23634fe/db10bf0638fa2bea3f88a8b654c7fa6a/jdk16.0.2.7.tar.gz).


### Supported Windows Versions

- Windows 10
- Windows Server 2016

### Supported Garbage Collectors
- Serial GC
- Parallel GC
- G1 GC
- ZGC
- Shenandoah GC

### FAQ

#### Is this build TCK'ed?

Yes.

#### Where can I test this build?

We have uploaded our Arm64 test systems information [here](https://github.com/microsoft/openjdk-aarch64/blob/master/Arm64_systems.md). You can find retail laptops with ARM64 and Windows, such as HP Enxy x2, Asus NovaGo, and the Microsoft Surface Pro X.

For additional information, please visit the [Works on Arm](https://www.worksonarm.com/?_ga=2.204290832.1614868344.1591633956-103015898.1581534333) website.

#### What Java tools run on this build?

The following tools have been tested, though not extensively, and did not show any immediate issues:

- Apache Maven
- Apache Ant
- Gradle
- Visual Studio Code Java Extension Pack

### Build dependencies

We rely on VS 2019 and the following individual components:
-	MSVC v142 - VS 2019 C++ ARM64 build tools (latest)
-	MSVC v142 - VS 2019 C++ x64/x86 build tools (latest)
-	C++ ATL for latest v142 build tools (ARM64)
-	C++ ATL for latest v142 build tools (x86 & x64)
-	C++ MFC for latest v142 build tools (ARM64)
-	C++ MFC for latest v142 build tools (x86 & x64)
-	Windows 10 SDK (10.0.18362.0)

Other dependencies are:
-	Cygwin
-	Boot and build JDK:
    - Java 11 is needed to build JDK 11
    - Java 16 is needed to build JDK 16

#### Building JDK 16 from github.com/openjdk/jdk.git

```shell
$ bash configure
          --openjdk-target=aarch64-unknown-cygwin
          --with-boot-jdk=<path-to-x86_64-JDK>
```
#### Building JDK 11

Note that the backport is not merged into the official OpenJDK repository yet. A recent version of our branch can be checked out from https://github.com/openjdk/jdk11u/pull/2.

Configure this way:
```
$ export DEVKIT="/cygdrive/c/work/VS2019-16.6.1-devkit"
$ export BOOTJDK="/cygdrive/c/work/jdk_x64_windows/jdk-11.0.10+8"
$ bash configure \
    --openjdk-target=aarch64-unknown-cygwin \  
    --with-devkit="$DEVKIT" \  
    --with-build-devkit="$DEVKIT" \  
    --with-build-jdk=$BOOTJDK \  
    --with-boot-jdk=$BOOTJDK
```

Note that:
* Devkit is required and must be created from a VS 2019 installation using the [make/devkit/createWindowsDevkit2019.sh](https://github.com/openjdk/jdk11u-dev/blob/master/make/devkit/createWindowsDevkit2019.sh) script.
* Both `build-jdk` _and_ `boot-jdk` must be specified.
* Since we are cross-compiling, the build must happen on a `x86_64` machine with the `--openjdk-target=aarch64-unknown-cygwin` specified as shown above.
* If you want to enable Shenandoah GC in this build, you have to explicitly enable it via: `--with-jvm-features=shenandoahgc`.
* The Arm64 flavor of the [fixpath binary](https://github.com/microsoft/openjdk-aarch64/releases/tag/fp-1.0) is available under the releases tab and has to be placed at the root of the source tree.

##### Why is this more complicated than on >= jdk16u?

The [WINENV patch](https://github.com/openjdk/jdk/pull/1597) that automatically supports the cross-compilation environment for Windows has not been backported to JDK 11u.


### OpenJDK binaries built by Microsoft for ARM64 devices

General Access (GA) Arm64 binaries are available for the following operating systems under the [releases](https://github.com/microsoft/openjdk-aarch64/releases) tab:


|        | Linux | Windows | MacOS |
|--------|-------|---------|-------|
| JDK 11 | [:floppy_disk:](https://github.com/microsoft/openjdk-aarch64/releases/download/jdk-11.0.12-ga/microsoft-jdk-11.0.12.7.1-linux-aarch64.tar.gz) | [:floppy_disk:](https://github.com/microsoft/openjdk-aarch64/releases/download/jdk-11.0.12-ga/microsoft-jdk-11.0.12.7.1-windows-aarch64.msi)<sup>1</sup> | :x:<sup>2</sup> |
| JDK 16 | [:floppy_disk:](https://github.com/microsoft/openjdk-aarch64/releases/download/jdk-16.0.2-ga/microsoft-jdk-16.0.2.7.1-linux-aarch64.tar.gz)   | [:floppy_disk:](https://github.com/microsoft/openjdk-aarch64/releases/download/jdk-16.0.2-ga/microsoft-jdk-16.0.2.7.1-windows-aarch64.msi)     | [:floppy_disk:](https://github.com/microsoft/openjdk-aarch64/releases/download/jdk-16.0.2-ga/microsoft-jdk-16.0.2.7.1-macos-aarch64.pkg)   |

<sup>1</sup> Upstreaming in progress.
<sup>2</sup> Coming soon.


## Feedback

Please send any emails to [aarch64-port-dev@openjdk.java.net](http://mail.openjdk.java.net/mailman/listinfo/aarch64-port-dev).

Microsoft is committed to working on an *upstream first* approach, so please reach out through the mailing list above. If you do want to contact the Microsoft team directly, please email openjdk-aarch64@microsoft.com.
