# PYNQ DPR Demo
# 这个Demo在PYNQ v2.7image和vivado 2019.1上实现了dynamic partial reconfiguration

## 参考了以下资料：
### project mode下的DPR：

https://www.youtube.com/watch?v=sgjPbaguWCg

### non-project mode下的DPR：

https://www.bilibili.com/video/BV1nW41137MQ

https://github.com/prevotet/Kerone/wiki/Hardware-Example-with-Partial-Reconfiguration

### 一个有关DPR的总结：
https://medium.com/%E9%AB%94%E9%A9%97%E4%BA%BA%E7%94%9F-touch-life/partial-reconfiguration-%E9%87%8D%E9%85%8D%E7%BD%AE-bb42a3f27edc

### 一个有关DPR的项目：

https://github.com/byuccl/PYNQ-PRIO

### 加减法IP：

https://pynq.readthedocs.io/en/v2.3/overlay_design_methodology/overlay_tutorial.html

https://www.bilibili.com/video/BV14p4y1Y7MK

### 死机的问题的讨论：

https://discuss.pynq.io/t/failed-on-a-simple-axi-lite-rm-with-partial-reconfiguration/833/3 

### xilinx文档：

https://china.xilinx.com/support/documentation/sw_manuals/xilinx2018_1/ug947-vivado-partial-reconfiguration-tutorial.pdf

https://www.xilinx.com/support/documentation/sw_manuals/xilinx2020_1/ug947-vivado-partial-reconfiguration-tutorial.pdf

https://www.xilinx.com/support/documentation/sw_manuals/xilinx2021_2/ug909-vivado-partial-reconfiguration.pdf

https://www.xilinx.com/support/documentation/sw_manuals/xilinx2019_2/ug835-vivado-tcl-commands.pdf


### 视频链接：
https://www.bilibili.com/video/BV1Db4y1s7f6/

### 用到的tcl命令：

set_param project.enablePRFlowIPI 1

set_param bitstream.enablePR 2341

set_param hd.enablePR 1234

set_property PR_FLOW true [current_project]

create_reconfig_module -name rm_sub -partition_def [get_partition_defs pd_0] -define_from rm_sub

### 问题：

#### 1.为什么部分位流加载之后查询到的IP是None？
#### 2.pr里边的rm的address应该怎么配置
#### 3.https://www.xilinx.com/support/documentation/sw_manuals/xilinx2021_2/ug909-vivado-partial-reconfiguration.pdf 第4章P87 P88 P89
#### 4.Partial Reconfiguration Decoupler是怎么用的
#### 5.视频中提到的如果只有一个pr读写mmio时会死机的问题