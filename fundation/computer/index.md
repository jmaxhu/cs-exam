# 计算机基础

## CPU

### CPU 频率

由于 CPU 与内存之间的存取速度不一致，导致 CPU 有主频，倍频和外频的概念。其中外频是 CPU 外部的频率，即与内存通讯的频率，主频即 CPU 内部的实际运行的频率。倍频=主频/外频。

### CPU 与 DSP

从表面上来看，DSP 与标准微处理器有许多共同的地方：一个以 ALU 为核心的处理器、地址和数据总线、RAM、ROM 以及 I/O 端口，从广义上讲，DSP、微处理器和微控制器（单片机）等都属于处理器，可以说 DSP 是一种 CPU。但 DSP 和一般的 CPU 又不同：

- 体系结构

  CPU 是冯.诺伊曼结构的，而 DSP 有分开的代码和数据总线即 “[哈佛结构](https://zh.wikipedia.org/wiki/%E5%93%88%E4%BD%9B%E7%BB%93%E6%9E%84)”。

## 串行总线和并行总线

串行总线每次传输一个比特数据，并继续进行以上单次过程的通信方式。并行总线一次可以传输多个比特。串行通信被用于长距离通信及大多数计算机网络。

串行通信构架的例子：RS-232、RS-422、通用串行总线、IEEE1394、以太网、SATA、PCI-EXPRESS 等。

## 嵌入式系统

嵌入式系统低功耗软件方面的优化主要包括如下几点：

1. 软硬件协同设计，即软件的设计要考虑与硬件的匹配，考虑硬件因素。
2. 编译优化，采用低功耗的编译技术。
3. 减少系统的持续运行时间，从算法角度进行优化。
4. 用“中断”代替“查询”。
5. 进行电源的有效管理。

## CRC 校验码

全称循环冗余校验码(Cyclic redundancy check)。CRC 是一种根据网络数据包或计算机文件等数据产生简短固定位数校验码的一种散列函数，主要用来检测或校验数据传输或者保存后可能出现的错误。生成的数字在传输或者存储之前计算出来并且附加到数据后面，然后接收方进行检验确定数据是否发生变化。

### CRC 计算步骤

1. 先选择一个除数，一般用一个多项式表示，生成一个二进制串。
2. 根据步骤 1 中选择的除数，把位数减去 1，得到一个少一位的全是 0 的数，并把这个数添加到待发送的信息码后面。
3. 把步骤 2 中的数除步骤 1 中的数（模 2 除数），得到一个余数，如果余数位数不足，则前面补 0 到 1 中位数减 1.这个余数就是 CRC 校验码。

## 题目

### 1. 2018 下半年架构师

![题目1](./imgs/ex-2018-2_9.png)

答案：B

解析：DSP 有分开的代码和数据总线，即：“哈佛结构”。

![题目2](./imgs/ex-2018-2_10.png)

答案：B

解析：A 中的一般都是全双工不正确。C 可以有校验位，但不能纠正。D 明显错误。

![题目3](./imgs/ex-2018-2_11.jpg)

答案：D

解析：根据嵌入式软件低功耗设计的 5 点对照，应采用，软硬件协同，编译优化和算法优化。

![题目4](./imgs/ex-2018-2_12.jpg)

答案：A

解析：主频=外频*倍频 200M * 13 = 2.6G

![题目5](./imgs/ex-2018-2_13.png)

答案： B

解析：根据给定的多项式，得到除数为：101011(6 位)，得到 CRC 校验码肯定是 5 位（6-1），计算时在给定的信息码后面加上 5 个 0，得到 11100011000000，把这个数用模 2 除法去除除数 101011，得到结果为：11001，刚好 5 位。所以答案为 B。
