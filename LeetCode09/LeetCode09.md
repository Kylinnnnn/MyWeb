这题比较简单，我就想稍稍考虑下该如何达到最高效率，前后共想了三种思路。
**思路一**：最简单的将数字先转成字符串，然后滑动窗口从头尾一一核对。这种方法虽然最简单，但感觉效率应该是最差，毕竟中间多了一个转换过程。
下面两个思路是看到题目描述进阶要求里问，如果不转换成数字该如何实现。
**思路二**：基于回文数的定义，我首先想到的是将数字先反转，如果反转前后相等那肯定就是回文数了。最后运行结果是`8ms`。在这种思路中反转过程中的需要遍历整个数字每一位，于是我就感觉可以再简化一下。
**思路三**：这个思路是基于思路二中想到的，回文数的前半截和后半截必然是相反的。因此只需要反转数字的后半截，然后判断是否与前半截相等即可。但此种方法需要剔除的特殊情况较第二种思路要多，所有`10`的倍数需要直接判为`false`，而`0`要判为`true`。最后运行结果为`12ms`。感觉结果效率更低可能是由于判断较多外加我另写了功能函数，导致寻址操作较多降低了效率。但那些判断我确实没能想出有什么较好的处理办法。
然后我又把官方题解跑了下，`16ms`。真不知道那些`2ms`左右的答案是什么神仙代码。
总的来看，空间复杂度和时间复杂度都只是数倍的关系，都在一个量级上。
**空间复杂度**：
$$O(n)$$
**时间复杂度**：
$$O(1)$$