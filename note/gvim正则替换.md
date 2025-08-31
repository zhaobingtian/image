

# 前言

前几天遇到一个替换memory的使用需求，因为这块memory比较特殊，仿真的时候一些特定的位置需要在testbench中force很多特定的值，才能达到仿真的需求，当时是用得gvim的正则替换快速替换的，简单记录一下操作

# 使用需求

原本的testbench大致是如下的样子，由于替换了新的memory model，导致hierarchy发生变化

![](https://raw.githubusercontent.com/zhaobingtian/image/main/pico/image-20250831211959128.png)

预期替换的样式如下：

- 信号hierarchy需要替换成新的
- 原本的mem因为拆分成两份，需要对两份instance都进行force赋值

![](https://raw.githubusercontent.com/zhaobingtian/image/main/pico/image-20250831212506270.png)



# 替换方法

gvim所用到的替换指令如下：

```shell
:%s/\(.*\)mem_model\.MEM\(.*\)\/\1mem_inst0\.mem_array\2\r\1mem_inst1\.mem_array\2/g
```



gvim用到的替换指令截图如下：

![](https://raw.githubusercontent.com/zhaobingtian/image/main/pico/image-20250831212601786.png)



gvim的 **\1**用法一直只是会用，具体的介绍还没研究过，这两天打算看看gvim对 **\1**用法的介绍，下次再记录发出来

