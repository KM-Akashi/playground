# Expectation Maximum
期望最大化

---

## 定义
事件数(N个): A,B,C...
事件数(M个): 1,2,3...
样本数(X个): S1,S2,S3...

## 设计
prob表：
|   | P1 | P2 | P3 | ... |
| - | - | - | - | - |
| A | Pa1 | Pa2 | Pa3 | ... (行和为1) |
| B | Pb1 | Pb2 | Pb3 | ... (行和为1) |
| C | Pc1 | Pc2 | Pc3 | ... (行和为1) |
| ... | ... | ... | ... | ... |

样本表：
|   | P1 | P2 | P3 | ... |
| - | - | - | - | - |
| X1 | S11 | S12 | S13 | ... |
| X2 | S21 | S22 | S23 | ... |
| X3 | S31 | S32 | S33 | ... |
| ... | ... | ... | ... | ... |


## E步
将S1行与prob表各行进行计算
```
P(X1 | A) = P(S11 | A) + P(S12 | A) + P(S13 | A) + ...
P(S11 | A) = C(count(X1),count(S11)) * Pa1 ^ count(S11) * (1-Pa2) ^ (count(X1) - count(S11))
```
|   | A | B | C | ... |
| - | - | - | - | - |
| X1 | P(X1\|A) | P(X1\|B) | P(X1\|C) | ... (最大的列即行所属类别)|
| X2 | P(X2\|A) | P(X2\|B) | P(X2\|C) | ... (最大的列即行所属类别)|
| X3 | P(X3\|A) | P(X3\|B) | P(X3\|C) | ... (最大的列即行所属类别)|
| ... | ... | ... | ... | ... |

## M步
统计同类样本，重新更新prob表。