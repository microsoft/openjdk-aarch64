|Workload| Tests |  Arm64 | Comments  | 
|:--:|:--:|:--:|:--:|
| SPECJBB2015 |  |o*  | Performance difference observed on a TX2 running Linux | 
| SPECJBB2005 |  | o* | Performance difference observed on a TX2 running Linux |  
| SPECJVM2008 | crypto, xml, derby, compress, etc | o* | startup doesn't work on JDK8+ (we are at JDK16/current tip) | 
| SPEC SERT | CPU/LU/SORT/SSJ/Flood3/Capacity/compress/Sha256 |o* |Benchmark changes made to accomodate the new platform combo, upstream to SPEC, benchmark needs fixing with removal of Nashorn| 
| DaCapo Benchmark | avrora fop h2 jython luindex lusearch lusearch-fix pmd sunflow tomcat xalan  | o* | one benchmark utilizes an x86-64 dll. A few others don't work on JDK8+. Lower priority |
| Scimark2 |  |o  |  | 
|Java MicroBenchmark Harness (JMH) | many microbenchmarks used for performance and implementation testing | o* | Haven't performance tested every combo. This will be test as you need. We have high confidence that these will work on Arm64 |
|Java Regression Testing Framework (JTREG)| tier1s are working, enabling more tests and expanding coverage to incorporate all tests that are currently running on JDK16| o*| We are enabling more tests every week and fixing bugs as we encounter them|
|The Computer Benchmarks Game|10 Java sub-benchmarks| x|Enablement and characterization work has started |

_Key to Status:_
|Legend| Status |
|--|--|
| o | Complete |
| o* | Almost there, see notes |
| x | Incomplete | 
