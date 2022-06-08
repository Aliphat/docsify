# 呼叫中心系统

## 对接线路，部署呼叫中心

[WebRTC + JsSIP + freeSWITCH一对一语音聊天](https://www.cnblogs.com/gxp69/articles/12028002.html)

[jssip中文开发文档（完整版） ](https://www.cnblogs.com/benmumu/p/8316670.html)

[三汇语音网关产品介绍说明图](https://www.dsliu.com/products/synway/)

[磐石云呼叫中心添加O口网关](PSCC.md)

[光猫开通反极信号](Fanjixinhao.md)

[三汇语音网关对接](Sanhui.md)

### 呼叫中心运维

[呼叫中心的知识库](knowledge.md)

[呼叫中心设备](ipgateway.md)

[FreeSWITCH中文网,电话机器人开发网](http://www.freeswitch.net.cn/index.html)

[如何从零搭建外呼系统](http://www.woshipm.com/pmd/1210429.html)

FreeSwitch软电话服务

磐石云以及二开接口。vue大屏







### VOS相关

[安装VOS](vos_install.md)

[使用VOS](vos_use.md)

[VOS官方指导文档](https://www.linknat.com/#/support/download)

[VOS6最新很详细的安装](vos6install.md)

[Vos安全防护相关的内容](vosSafe.md)

## 本地电话呼叫转移

### 呼叫转移设置方法如下：

1. 拨打*41*DN#设置无应答转移，拨打#41#取消无应答转移。
2. 拨打*40*DN#设置遇忙转移，拨打#40#取消遇忙转移。
3. 拨打*57*DN#设置无条件转移，拨打#57#取消无条件转移。

### 温馨提醒：	

1. DN表示需转移的号码。
2. 呼叫转移产生的通话费按固话正常通话费缴纳，若办理的套餐有分钟数，呼叫转移所产生的分钟数按正常计费规则进行抵扣。

## 本地线路上云方案
### 方案一:运营商为模拟线路
线路要求:运营商根据客户需求通过小交连选等方式实现多条模拟线对应同一个联通接入号，实现多人同时拨打该号码能依次给多条电话线振铃。
设备要求:用户侧提供O口模拟网关与联通模拟线对接，且模拟网关接入任何能访问云主机的互联网网线。

### 方案二:联通提供公网上的SIP线路，比如联通BPO业务
线路要求:
1 联通将用户指定固话号做到联通BPO平台
2 联通BPO平台提供公网注册地址，用户名及密码。
设备要求: 无需其他设备，云主机直接向联通sip注册。

### 方案三:联通提供内网上的SIP线路，类似于移动IMS业务。
设备要求:
1 用户侧提供一台双网卡物理服务器或台式机，操作系统为windows7及以上或centos6.5及以上。
2 物理服务器或台式机一个网卡接能放问云主机的互联网网线。
3 物理服务器或云主机另一个网卡接联通内网(语音专线)网线。
线路要求:
1 联通提供可供号码注册的内网(或语音专线)，提供终端设备(服务器或台式机)使用的ip地址
2 联通提供内网注册地址，用户名及密码。




## 工单系统

### 1.[联傲云工单系统](http://www.chainall.com/)  大几十万

大而全，可定制化，微信派单，功能成熟。就是贵。

### 2.12345青岛工单系统

来自psc老哥，目前正在咨询中
据说，预算至少5w


### 3.JeecgBoot

大体上粗略一看，还没有研究明白



## 电话线无法通过O口网关连接到话务系统服务器？

答：O口网关跟话务系统服务器要选择相同的加密方式。

打不出电话去？

答：用SIP软电话检查O口网关是否注册好，没有注册好的好，先配置好O口网关，如果注册好的话，检查S口网关能不能收到电话信号，收不到检查S口网关是否注册到话务系统服务器，确保S端口对应的sip注册成功，然后检查是否能通话。

接电话62秒之后自动挂断？

答：在一分钟的时候，语音网关话务系统服务器发来的挂断的语音包，修改话务系统服务器设置。

接电话正常通话40秒、十分钟之后没有声音，但电话没有挂断？

原因：一段时间之后 s口网关收不到服务器发来的rtp数据包；接受语音的网络端口号，会发生改变，目前还是不知道什么原因造成的。


