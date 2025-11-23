# 0 前言

前段时间在替换一些文档时，因为有部分新文档的文档名和旧的重复，在执行`cp`指令时特意加了`-f`的option，但还是会提示要确认，研究了一下，顺便做个记录

# 1 介绍两个option

介绍下Linux `cp`指令的两个option

| option | description                                        |
| ------ | -------------------------------------------------- |
| -i     | 在覆盖已存在的目标文件前，强制弹出确认提示         |
| -f     | 忽略文件属性限制，直接覆盖目标文件，跳过交互式提醒 |

![](https://raw.githubusercontent.com/zhaobingtian/image/main/pico/image-20251123213054291.png)

# 2 解决方法

如果遇到执行 `cp -f`还是会弹出确认提示，大概率是环境中为`cp`指令添加alias

```bash
# 执行如下cmd
which cp
```

如果有添加alias，会弹出如下内容

![](https://raw.githubusercontent.com/zhaobingtian/image/main/pico/image-20251123214724794.png)

可以修改alias，把`cp -i`拿掉，不过一般还是保留比较好，避免误覆盖非预期文件

另一种方法，可以执行如下cmd

```bash
\cp -f
```

在`cp`前加`\`Linux会忽略alias，直接调用Linux原生的`cp`指令





# 往期内容

[SystemVerilog避坑——logic初始化问题](https://mp.weixin.qq.com/s/cCehflwKlfE3eLjQeD4HoA)

[记录一个gvim正则替换的例子](https://mp.weixin.qq.com/s/CEYEhonVRN-U5uw3fO-Drw)

[verdi从波形界面获取信号hierarchy的方法](https://mp.weixin.qq.com/s/N3lDRmyT4lCmYe_sGTcw8Q)

[gvim去除重复行、跳到指定列和换行设定](https://mp.weixin.qq.com/s/l2MU1bzmcrEagkwhCUnC2A)

[gvim批量替换的进阶操作](https://mp.weixin.qq.com/s/AZfyjUDg8xLQtSoCuvgSeg)

[gvim列替换和垂直分割](https://mp.weixin.qq.com/s/Mp8RpEEybjqVtMfHo2FxYg)