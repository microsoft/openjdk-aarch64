OpenJDK for Windows 10 ARM64
=====

This project only holds early access binaries of the initial port of OpenJDK for Windows on ARM64 devices and some accompanying documentation.

* See our [Contributing Guide](CONTRIBUTING.md).  **Please note** source code contributions are welcome through the [OpenJDK project](https://openjdk.java.net/contribute/). 
* Our [Code of Conduct](CODE_OF_CONDUCT.md).

*Early Access* binaries are available in the [releases](https://github.com/microsoft/openjdk-aarch64/releases) tab for experimentation.

## JDK Enhancement Proposal
The JEP can be found at [https://openjdk.java.net/jeps/388](https://openjdk.java.net/jeps/388).

This JEP was tracked under the [JDK-8248496](https://bugs.openjdk.java.net/browse/JDK-8248496) work item and has been delivered in JDK 16.

## Source Code
All source code changes to OpenJDK, that were required to implement this port, were being tracked under [JDK-8248238 Implementation of JEP: Windows AArch64 Support](https://bugs.openjdk.java.net/browse/JDK-8248238).

The source code is merged into JDK 16 and is now a part of the [OpenJDK project](https://github.com/openjdk/jdk). 
Here's a [link to the source code for our JDK 16u EA build](https://download.visualstudio.microsoft.com/download/pr/df5d5fd6-decb-4eea-8c08-895c5b088439/edb7b06196fae4471a3c241e092f2eda/jdk16u.tar.gz).


## Supported Windows Versions

- Windows 10
- Windows Server 2016

## Supported Garbage Collectors
- Serial GC
- Parallel GC
- G1 GC
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
- Visual Studio Code Java Extension Pack

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

### Building from github.com/openjdk/jdk.git

```shell
$ bash configure
          --openjdk-target=aarch64-unknown-cygwin
          --with-boot-jdk=<path-to-x86_64-JDK>
```
### Build from JDK11

(Note that the backport is not merged yet, a branch exists here: https://github.com/openjdk/jdk11u/pull/2 )

Configure this way:
```
$ DEVKIT="/cygdrive/c/work/VS2019-16.6.1-devkit" \
    BOOTJDK="/cygdrive/c/work/jdk_x64_windows/jdk-11.0.10+8" \
     bash configure \
    --openjdk-target=aarch64-unknown-cygwin \  
    --with-devkit="$DEVKIT" \  
    --with-build-devkit="$DEVKIT" \  
    --with-build-jdk=$BOOTJDK \  
    --with-boot-jdk=$BOOTJDK
```

Note that:
* Usage of a devkit is required. Must be created from a VS2019 installation. The jdk11u repository only contains a script for VS2017, so one from e.g. jdk16u has to be used: https://github.com/openjdk/jdk16u/blob/master/make/devkit/createWindowsDevkit2019.sh
* Both `build-jdk` _and_ `boot-jdk` must be specified.
* Build must happen on a `x86_64` machine.
* If you want to enable ShenandoahGC in this build, you have to explicitly enable it via: `--with-jvm-features=shenandoahgc`.

#### Why is this more complicated than on >= jdk16u?

Because the WINENV patch has not been backported which adds proper cross-compilation for Windows: https://github.com/openjdk/jdk/pull/1597

## Feedback

Please send email to [aarch64-port-dev@openjdk.java.net](http://mail.openjdk.java.net/mailman/listinfo/aarch64-port-dev). 

Microsoft is committed to working on an *upstream first* approach, so please reach out through the mailing list above. If you do want to contact the Microsoft team directly, please email openjdk-aarch64@microsoft.com.
