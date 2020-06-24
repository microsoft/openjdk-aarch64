OpenJDK for Windows 10 ARM64
=====

This project holds only early access binaries of the initial port of OpenJDK for Windows on ARM64 devices. 

The source code can be found upstream on [openjdk.java.net](https://openjdk.java.net). 
Contributions are welcome through the [OpenJDK project](https://openjdk.java.net/contribute/).

*Early Access* binaries are available in the [releases](https://github.com/microsoft/openjdk-aarch64/releases) tab for experimentation.

## Suppported Windows Versions

- Windows 10 (build ###)
- Windows Server 2016 (build ###)

## Known Limitations

- Supported Garbage Collectors
  - SerialGC
  - ParallelGC

*ParallelGC is set as the default GC until G1GC has been fixed.*

### Work in Progress

- G1GC
- AWT/Swing

## FAQ

### Is this build TCK'ed?

Early Access binaries will not be TCK'ed. 

### Where can I test this build?

You can find retail laptops with ARM64 and Windows, such as HP Enxy x2, Asus NovaGo, and the Microsoft Surface Pro X.

For more information, please visit [Works on Arm](https://www.worksonarm.com/?_ga=2.204290832.1614868344.1591633956-103015898.1581534333) website.

### What Java tools run on this build?

The following tools have been tested, though not extensively, and did not show any immediate issues:

- Apache Maven
- Apache Ant
- Gradle
- Visual Studio Code Java Extension Pack (note: must change configurations to use Parallel GC)

## Feedback

Please email to [aarch64-port-dev@openjdk.java.net](http://mail.openjdk.java.net/mailman/listinfo/aarch64-port-dev). 

Microsoft is committed to work on an *upstream first* approach, so please reach out through the mailing list above. If you do want to contact the Microsoft team directly, please email openjdk-aarch64@microsoft.com.
