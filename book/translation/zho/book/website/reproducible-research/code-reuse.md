(rr-code-reuse)=
# 可重用代码
Your software project could range from a small script you use for data processing to a notebook used for data analysis, or a software library implementing your algorithms. Regardless of how big or small your software project is, it is important to make your code reusable.

Different types of software have different requirements for being reusable: for a small script, having sufficient documentation might be enough, while for a mission critical software library, thorough testing might be necessary. At the most basic level, all you need to do is put your code online somewhere that is likely to last a long time. A more elaborate approach to making your research software more reusable is by following the FAIR Principles for Research Software (FAIR4RS Principles) {cite:ps}`ChueHong2021FAIR4RS`.

当我们谈论使代码可重复使用时，澄清我们的含义是有益的。 In the {ref}`Table of Definitions for Reproducibility<rr-overview-definitions-reproducibility>` we defined reproducible research as using the same data and the same code. 然而，当我们谈到代码的重新使用时，这可能需要多种形式：我们可能想要运行完全相同的代码(对于编译的编程语言)。 这甚至可能意味着完全相同的二进制文件， 或者我们可能希望修改源代码并以某种特定方式加以扩展以满足我们的需要。 Freire and Chirigati {cite:ps}`Freire2018Reproducibility` provide a framework of different levels of reproducibility, depending on what can be modified. They define the following levels of reproducibility: repeatable, re-runnable, portable, extendable and modifiable.

We can map the definitions of reproducibly on the Freire framework as follows:

| Freire framework | Definitions of reproducibly                                         |
| ---------------- | ------------------------------------------------------------------- |
| Repeatable       | Reproducible (same data, same analysis)                             |
| Re-runnable      | Robust & Replicable (same code, different data/analysis/parameters) |
| Portable         | *未被考虑* (相同的代码/数据，不同的环境)                                             |
| Extendable       | (partly) Generalisable                                              |
| Modifiable       | (partly) Generalisable                                              |

Portability was not previously considered, but for software a different environment (such as different hardware, operating system or even a fresh install on comparable hardware) may affect the ability for the software to work (for example it may affect dependencies).

此外，可普遍封装的两个概念：可扩展(与其他软件结合的能力) 和可修改(能够改变部分实现以扩大其功能)。

In the rest of this chapter we provide list of recommendations you can follow to make sure your code is reusable.
