## With Latest Refactoring on current tip = JDK16:
### Parallel GC
|Test system  | Hardware | Patch combo| hbIR max | hbIR settled | max-JOPS  |  critical-JOPS|
|--|--|--|--|--|--|--|
| linux-aarch64  | TX2 | refactored P1  | 100% |	98%	| 94%	| 49% |  
| linux-aarch64  | TX2 | refactored P1 + P2 |  100% |	97%	| 94%	| 50%  |  
||||||||
| windows-aarch64  | TX2 | P1 + P2 + P3 + P4 |  100% |	88%	| 83%	| 40%  | 
||||||||
| windows-x86-64  | Skylake | refactored P1 |  100% |	90%	| 85%	| 27%  |  
| windows-x86-64  | Skylake | refactored P1 + P2 | 100% |	90%	| 85%	| 27% |

### G1 GC
|Test system  | Hardware | Patch combo| hbIR max | hbIR settled | max-JOPS  |  critical-JOPS|
|--|--|--|--|--|--|--|
| linux-aarch64  | TX2 | refactored P1  | 100% |	97%	| 92%	| 51% |  
| linux-aarch64  | TX2 | refactored P1 + P2 |  100% |	95%	| 89%	| 49%  |  
||||||||
| windows-x86-64  | Skylake | refactored P1 |  100% |	84%	| 79%	| 26%  |  
| windows-x86-64  | Skylake | refactored P1 + P2 | 100% |	84%	| 80%	| 27% |

## With all 4 patches when tip was JDK15:

### Parallel GC
|Test system  | Hardware | Patch combo| hbIR max | hbIR settled | max-JOPS  |  critical-JOPS|
|--|--|--|--|--|--|--|
| linux-aarch64  | TX2 | Baseline | 100% |	83%	| 55%	| 10% |
| linux-aarch64  | TX2 | P1 | 100% |	83%	| 64%	| 10% |  
| linux-aarch64  | TX2 | P1 + P2 |  100% |	83%	| 60%	| 12%  |  
| linux-aarch64  | TX2 | P1 + P2 + P3 |  100% |	83%	| 55%	| 12%  | 
| linux-aarch64  | TX2 | P1 + P2 + P3 + P4 |  100% |	83%	| 65%	| 10%  | 
||||||||
| windows-aarch64  | TX2 | P1 + P2 + P3 + P4 |  100% |	88%	| 82%	| 39%  | 
||||||||
| windows-x86-64  | Skylake | Baseline |  100% |	91%	| 84%	| 27%  |  
| windows-x86-64  | Skylake | P1 + P2 + P3 + P4 | 100% |	90%	| 84%	| 29% |

### G1 GC
|Test system  | Hardware | Patch combo| hbIR max | hbIR settled | max-JOPS  |  critical-JOPS|
|--|--|--|--|--|--|--|
| linux-aarch64  | TX2 | Baseline | 100% |	97%	| 88%	| 49% |
| linux-aarch64  | TX2 | P1 | 100% |	94%	| 82%	| 48% |  
| linux-aarch64  | TX2 | P1 + P2 |  100% |	95%	| 88%	| 49%  |  
| linux-aarch64  | TX2 | P1 + P2 + P3 |  100% |	95%	| 88%	| 49%  |
| linux-aarch64  | TX2 | P1 + P2 + P3 + P4|  100% |	95%	| 82%	| 49%  | 
||||||||
| windows-x86-64  | Skylake | Baseline |  100% |	84%	| 79%	| 26%  |  
| windows-x86-64  | Skylake | P1 + P2 + P3 + P4 | 100% |	85%	| 79%	| 26%  |

