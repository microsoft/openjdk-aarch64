## JTReg with P1 and P2 refactoring and JDK 16 as tip:
### Windows-aarch64 with refactored P1 and P2
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
| jtreg:test/hotspot/jtreg:tier1   | 1295 | 1279  |  16  |   0 |
| jtreg:test/jdk:tier1   | 1931 | 1915  |  16  |   0 |
| jtreg:test/jdk:tier2 | 3609 | 3564 | 45 | 0  |
| jtreg:test/langtools   | 4085 | 4076  |   9  |   0 |
____________________________________________________________
____________________________________________________________
### Linux-AArch64 with refactored P1 patch
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1 |  1598 | 1597|  1 | 0 |
 |  jtreg:test/jdk:tier1| 1924 | 1924 |  0 |  0 |
| jtreg:test/jdk:tier2| 3586 | 3583 |  1  | 2 |
| jtreg:test/langtools:tier1| 4049 |4049 |  0  |  0 |
| jtreg:test/langtools:tier2|   11 | 11  | 0  | 0|

### Linux-AArch64 with refactored P1+P2 patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1 |  1598  | 1595 | 2  | 1  | 
|jtreg:test/jdk:tier1 |  1924 | 1923  |   0 |  1  | 
| jtreg:test/jdk:tier2  | 3586 | 3583 |  1  |  2  | 
| jtreg:test/langtools:tier1  | 4049 | 4049   |  0  |  0  | 
| jtreg:test/langtools:tier2 | 11  |  11  |  0  |  0 | 
____________________________________________________________
____________________________________________________________
### Windows-x86-64 with refractored P1
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1   | 1625 | 1567|  58 |  0 | 
|jtreg:test/jdk:tier1  | 1934| 1934 |   0|   0 | 
|jtreg:test/jdk:tier2  | 3607| 3603|  4|  0 | 
|jtreg:test/langtools:tier1|  4065| 4063|  2 |  0 | 
|jtreg:test/langtools:tier2|  12 | 12 |  0 |  0|  

### Windows-x86-64 with refractored P1 + P2
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1  | 1625 | 1567 | 58 |  0 |
|jtreg:test/jdk:tier1  | 1934 | 1934 | 0 |  0 |
|jtreg:test/jdk:tier2  | 3608 | 3604 | 4 |  0 |
|jtreg:test/langtools  | 4080 | 4078 | 2 |  0 |

## Previous JTReg results with JDK15 as tip:
### Linux-AArch64 Baseline (without patches)
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1  | 1598 |1597  |1  | 0 |
| jtreg:test/jdk:tier1 | 1924 | 1924 | 0 | 0 |
| jtreg:test/jdk:tier2  | 3586 | 3582 | 2 | 2 |
| jtreg:test/langtools:tier1  | 4049 | 4049 | 0 | 0 |
| jtreg:test/langtools:tier2  | 11 | 11 | 0 | 0 |

### Linux-AArch64 with P1 patch
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1 |  1598 | 1597|  1 | 0 |
 |  jtreg:test/jdk:tier1| 1924 | 1924 |  0 |  0 |
| jtreg:test/jdk:tier2| 3586 | 3582 |  2  | 2 |
| jtreg:test/langtools:tier1| 4049 |4046 |  3  |  0 |
| jtreg:test/langtools:tier2|   11 | 11  | 0  | 0|

### Linux-AArch64 with P1+P2 patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1 |  1598  | 1595 | 2  | 1  | 
|jtreg:test/jdk:tier1 |  1924 | 1923  |   0 |  1  | 
| jtreg:test/jdk:tier2  | 3586 | 3583 |  1  |  2  | 
| jtreg:test/langtools:tier1  | 4049 | 4046   |  3  |  0  | 
| jtreg:test/langtools:tier2 | 11  |  11  |  0  |  0 | 

### Linux-AArch64 with P1+P2+P3 patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1|1598 |1595| 2|1|
| jtreg:test/jdk:tier1|  1924 |1923|  0| 1 |
| jtreg:test/jdk:tier2 |  3586 |3583| 1 | 2 |
| jtreg:test/langtools:tier1|4049| 4046| 3| 0 |
| jtreg:test/langtools:tier2|  11| 11| 0 | 0|

### Linux-AArch64 with all the patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
| jtreg:test/hotspot/jtreg:tier1  | 1598   | 1595   |  2   |  1  | 
| jtreg:test/jdk:tier1  | 1924  | 1923  |  0   |  1   | 
|jtreg:test/jdk:tier2   | 3586  | 3583  |  1   | 2   | 
|jtreg:test/langtools:tier1   | 4048  | 4045   | 3   |  0   | 
| jtreg:test/langtools:tier2   |  11  |  11  |  0  |  0  | 

____________________________________________________________
____________________________________________________________

### Windows-x86-64 P1 only
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1   |  1578| 1520|  58 |  0 | 
|jtreg:test/jdk:tier1  | 1926| 1925 |   1|   0 | 
|jtreg:test/jdk:tier2  | 3595| 3564|  31|  0 | 
|jtreg:test/langtools:tier1|  4045| 4041|  4 |  0 | 
|jtreg:test/langtools:tier2|  12 | 12 |  0 |  0|    

### Windows-x86-64 with P1+P2 patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1| 1578|1519 |59 | 0 |
|jtreg:test/jdk:tier1| 1926|1925 | 1| 0 |
|jtreg:test/jdk:tier2 |3595 |3564 | 31 | 0 |
|jtreg:test/langtools:tier1 |  4045| 4041| 4 | 0 |
|jtreg:test/langtools:tier2 | 12  | 12 | 0 | 0 |  

### Windows-x86-64 with P1+P2+P3 patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
|jtreg:test/hotspot/jtreg:tier1| 1578|1520 |58 | 0 |
|jtreg:test/jdk:tier1| 1926|1925 | 1| 0 |
|jtreg:test/jdk:tier2 |3595 |3563 | 32 | 0 |
|jtreg:test/langtools:tier1 |  4045| 4041| 4 | 0 |
|jtreg:test/langtools:tier2 | 12  | 12 | 0 | 0 |  

### Windows-x86-64 with all the patches
|Tests|Total  |Pass  | Fail | Error  |
|--|--|--|--|--|
| jtreg:test/hotspot/jtreg:tier1 | 1578 | 1518 | 60 | 0  | 
| jtreg:test/jdk:tier1 | 1926 | 1925 | 1 | 0  | 
| jtreg:test/jdk:tier2 | 3595 | 3563 | 32 | 0  | 
| jtreg:test/langtools:tier1 | 4045 | 4041 | 4  | 0  | 
| jtreg:test/langtools:tier2 | 12 | 12 | 0 | 0  | 
