### 1.3.4 服务原语（primitive）

LISTEN / CONNECT / RECEIVE / SEND / DISCONNECT，以及客户端-服务器端简单通讯的过程介绍。

为何不使用无连接协议？无法处理丢包、乱序等。


### 1.3.5 服务与协议的关系

服务是下层给上层的一组原语（操作、接口）。

协议是同层交换信息的格式和含义。



## 1.4 参考模型


### 1.4.1 OSI参考模型

* 应用层（application layer）（APDU）：直接针对用户需求。

* 表示层（presentation layer）（PPDU）：定义抽象的数据结构和编码方式。

* 会话层（session layer）（SPDU）：提供服务，如对话控制、令牌管理、同步功能等。

* 传输层（transport layer）（TPDU）：

* 网络层（network layer）（包）：控制子网的运行过程，将包从源端路由发送到目标端。

* 数据链路层（data link layer）（帧）：将发送方的输入数据拆开分装成数据帧，顺序传送数据帧。接收方发送确认帧（acknowledgement frame），确认每一帧都已正确收到。

* 物理层（physical layer）（bit）：保证一方发送“1”，另一方也能收到“1”。


### 1.4.2 TCP/IP参考模型

* 应用层（application layer）：对大多数应用不需要会话层和表示层。包含了所有的高层协议。类似于OSI的应用层。协议有TELNET，FTP，SMTP等

* 传输层（transport layer）：允许源和目标主机的对等体进行对话，类似于OSI传输层。协议有TCP和UDP。

* 互联网层（internet layer）：以无连接的互连网络层为基础，允许主机将包发送到任何网络，并让这些包独立地到达目标端（不包括顺序的重新排列），类似于OSI网络层。协议有IP。

* 主机至网络


### 1.4.3 OSI参考模型与TCP/IP参考模型

OSI三大核心：服务、接口、协议

OSI支持无连接和面向连接的通信，TCP/IP只支持无连接通信


### 1.4.4 OSI模型和协议的缺点

时机、技术、实现、政策

### 1.4.5 TCP/IP参考模型的缺点

没有清楚区分服务、接口、协议；不通用；主机至网络层不是一层而是一个接口；没有区分物理层和数据链路层。


## 1.5 网络实例

### 1.5.1 Internet

* ARPANET

* NSFNET

### 1.5.2 面向连接的网络：X.25、帧中继和ATM

### 1.5.3 以太网

### 1.5.4 无线LAN：802.11


## 1.6 网络标准化 1.7 度量单位 1.8 本书其余部分的概要 1.9 本章小结




# 二、物理层



## 2.1 数据通信的理论


### 2.1.1 傅里叶分析

傅里叶分解的数学公式


### 2.1.2 有限带宽的信号

通常，在从0到某个频率fc这一段范围内，振幅在传输过程中不会衰减，在此截止频率fc之上的频率所对应的振幅都会有不同程度的减弱。

传输过程中振幅不会明显减弱的这一段频率范围称为带宽。


### 2.1.3 信道的最大数据传输率

尼奎斯特定理：最大数据传输率 = 2H，H为信道带宽（单位Hz），数据传输率bps

信噪比为信号功率与噪音功率之比，记为S/N。信噪比单位为分贝，换算方式为 10 lg(S/N)

香农定理：最大数据传输率 = H(1+S/N)，H为信道带宽（单位Hz），S/N为信噪比（单位分贝）



## 2.2 有导向的传输介质

### 2.2.1 磁介质
### 2.2.2 双绞线
### 2.2.3 同轴电缆
### 2.2.4 光纤


## 2.3 无线传输


### 2.3.1 电磁波谱

跳频扩频（frequency hopping spread spectrum）：发送方每秒几百次地从一个频率跳到另一种频率。（难以检测，抵抗多路衰减）（WiFi、蓝牙）

直接序列扩频（direct sequence spread spectrum）


### 2.3.2 无线电传输

低频能穿透障碍物，但能量急剧衰减；高频直线传播，会受到障碍物阻挡；无线电波会被雨水吸收。


### 2.3.3 微波传输

微波按直线传播，需要中继器。

多路衰减（multipath fading）：大气层折射而迟到的微波和直接到达的微波不同相，因而抵消了信号。


### 2.3.4 红外线和毫米波

### 2.3.5 光波传输



## 2.4 通信卫星

### 2.4.1 地球同步卫星
### 2.4.2 中间轨道卫星
### 2.4.3 低轨道卫星
### 2.4.4 卫星和光纤


## 2.5 公共交换电话网络

### 2.5.1 电话系统的结构

三个主要部件：本地回路、干线、交换局

电话__本地回路__端局==长途局==中心交换局==长途局==端局__本地回路__电话


### 2.5.2 电话业中的政治学
### 2.5.3 本地回路：调制解调器、ADSL（非对称数字用户线路）和无线


### 2.5.4 干线和多路复用

频分多路复用FDM（frequency division multiplexing）

波分多路复用WDM（Wavelength division multiplexing）：属于频分多路复用

时分多路复用TDM（time division multiplexing）


### 2.5.5 交换



## 2.6 移动电话系统

### 2.6.1 第一代移动电话：模拟语音

### 2.6.2 第二代移动电话：数字语音

码分多路访问CDMA（code division multiple access）举例：

* A, B, C, D 4个移动站的时间片序列

A: 0 0 0 1 1 0 1 1

B: 0 0 1 0 1 1 1 0

C: 0 1 0 1 1 1 0 0

D: 0 1 0 0 0 0 1 0

* A, B, C, D 4个时间片序列的双极表示法（注意四个时间片序列两两正交）

A: -1 -1 -1 +1 +1 -1 +1 +1

B: -1 -1 +1 -1 +1 +1 +1 -1

C: -1 +1 -1 +1 +1 +1 -1 -1

D: -1 +1 -1 -1 -1 -1 +1 -1

* A, B, C, D 同时发送信息0,1或-（不发送）

--1-	C			S1 = -1 +1 -1 +1 +1 +1 -1 -1

-11-	B+C			S2 = -2  0  0  0 +2 +2  0 -2

10--	A+~B		S3 =  0  0 -2 +2  0 -2  0 +2

101-	A+~B+C		S4 = 略

1111	A+B+C+D		S5 = 略

1101	A+B+~C+D	S6 = 略

* 恢复站C，1代表发送了1，-1代表发送了0，0代表没发送

S1*C = (1+1+1+1+1+1+1+1)/8	= 1

S2*C = (2+0+0+0+2+2+0+2)/8	= 1

S3*C = (0+0+2+2+0-2+0-2)/8	= 0

S4*C = (略)/8				= 1

S5*C = (略)/8				= 1

S6*C = (略)/8				= -1


### 2.6.3 第三代移动电话：数字语音与数据


## 2.7 有线电视 2.8 本章小结



# 三、数据链路层


## 3.1 数据链路层的设计问题

1. 向网络层提供一个定义良好的服务接口
2. 处理传输错误
3. 调节数据流，确保慢速的接收方不会被快速的发送方淹没


### 提供给网络层的服务

* 无确认的无连接服务：错误率很低的场合、实时通信
* 有确认的无连接服务：不可靠的信道（如WiFi）
* 有确认的有连接服务


### 成帧

* 字节计数法

	如 1 2 3 | 1 2 3 4 5 -> **3** 1 2 3 | **5** 1 2 3 4 5
	
* 字节填充的标志字节法

	如 A ESC FLAG B -> **FLAG** A **ESC** ESC **ESC** FLAG B FLAG

* 比特填充的标志比特法

	1110 1111 1111 0111 -> **01111110** 1110 1111 1**0**111 0111 **01111110**
	
* 物理层编码违禁法：使用冗余比特


### 差错控制
### 流量控制


## 3.2 差错检测和纠正

* 纠错码（error-correcting code）：前向纠错（FEC，forward error correction）
* 检错码（error-detecting code）

错误类型：
* 孤立的单个比特错误
* 突发性的整片的错误


### 纠错码

* 海明码

	m个数据位，r个冗余位，码字（codeword）n为m+r，码率（code rate）为m/n。
	
	海明距离（Hamming Distance）：两个码字中不相同的位的个数。

	如 1000 001 -> **0** **0** 1 **0** 000 **1** 001

* 二进制卷积码
* 里德所罗门码
* 低密度奇偶校验码（LDPC，low-density parity check）


### 检错码

* 奇偶
* 校验和
* 循环冗余校验（CRC）



## 3.3 基本数据链路层协议

进程运行在网卡（网络接口卡，NIC，Network Interface Card）

帧四个字段：
* kind：区分控制信息帧和同时含有控制信息和数据信息的帧
* seq：序号
* ack：确认
* info：数据包


### 一个乌托邦式的单工协议

假设：信道永远不会损坏帧或丢失帧、双方网络层总是就绪、数据处理时间忽略、可用缓存无穷大。

描述：发送方不断地发，接收端不断地接。


### 无错信道上的单工停等式协议

描述：发送方发送一帧，接收方接收后发送确认帧，发送方接收确认帧后，再发下一帧


### 有错信道上的单工停等式协议

由于确认帧可能丢失，引入1位序号。

带有自动重复请求（ARQ，automatic repeat request）或重传的肯定确认（PAR，positive acknowledge with retransmission）

描述：发送方发送一帧，并开启计时器，如果在特定时间内收到确认帧，则计时结束；否则重复发送该帧。接收方接收帧，如果序号正确，返回确认帧，并加序号模二加一；否则丢弃。


## 滑动窗口协议

捎带确认（piggybacking）：暂时延缓确认以便将确认信息搭载在下一个出境数据帧上。

使用帧头的kind字段区分数据帧还是确认帧。

使用发送窗口（sending window）和接收窗口（receiving window）


### 1位滑动窗口协议

描述：发送方发送一帧，并开启计时器，如果在特定时间内收到确认帧，且应答序号和期待序号一致，则计时结束，期待序号加一；否则，重复发送。接收帧接收数据帧，如果序号和期待序号一致，则发送带确认的数据帧，开启计时器；否则丢弃帧。

同时发起通信时会发生错误。


### 回退N协议

### 选择重传协议


## 数据链路协议示例



	

# 四、介质访问控制（MAC，Medium Access Control）子层

广播信道：多路访问信道（multiaccess channel）或随机访问信道（random access channel）


## 4.1 信道分配问题


### 静态信道分配

传统做法：多路复用（如频分多路FDM），适用于用户数量少且固定，每个用户都有稳定的流量或负载。

在容量为C bps的信道上，发送一帧的平均时延为T，随机到达帧的速率为λ，平均每帧1/μ位，则满足

T = 1 / (μC-λ)

将单个信道分成N个独立信道，则

T_N = 1 / (μ(C/N)-(λ/N)) = NT。


### 动态信道分配的假设

* 流量独立（independent traffic）
* 单信道（single channel）
* 冲突可观察（observable collision）
* 时间连续或分槽（continuous or slotted time）
* 载波侦听或不听（carrier sense or no carrier sense）



## 4.2 多路访问协议


### ALOHA

1. 纯ALOHA：有数据需要发送时就发送。如果帧被损坏，则等待随机时间后再次发送。

S为吞吐量，G为每帧时的平均帧数，则有

S = G*e^(-2G)

2. 分槽ALOHA：到时间槽才能发送。

S = G*e^(-G)


### 载波侦听多路访问协议（carrier sense protocol）

1. 1-坚持载波检测多路访问（CSMA，carrier sense multiple access）：首先侦听信道，如果信道为空则立即（概率1）发送数据，否则等待直到信道为空之后立即发送。

* 等待后立即同时传输导致冲突。
* 一个站开始发送后，另一个站在第一个站发送信号到来之前侦听到信道为空，导致冲突。

2. 非坚持CSMA（nonpersistent CSMA）：首先侦听信道，如果信道不为空，则随机等待一段时间，再次侦听。

3. p-坚持CSMA（p-persistent CSMA）：适用于分时间槽的信道。首先侦听信道，如果信道为空则以概率p发送数据，否则推迟到下一个时间槽。

4. 带冲突检测的CSMA（CSMA/CD，CSMA with collision detection）：如果一个站检测到冲突，立即中止传送，等待随机时间后再次重新尝试传送。

假设相距最远的站传播信号所需时间为τ，在t0时间一个站开始传送数据。如果它在t0到t0+2τ时间内没有监听到冲突，则可确保自己抓住信道。（相当于2τ时间槽的分槽ALOHA系统）


### 无冲突协议

1. 位图协议：基本位图法（basic bitmap method）：传输数据前先广播自己有发送数据愿望（此类协议称为预留协议，reservation protocol），它无法很好地扩展到较大的网络。

	* 低负载情况下：数据长度为d，每一帧的额外开销为N，信道利用率为d/(N+d)

	* 高负载情况下：N=1，信道利用率为d/(d+1)

2. 令牌（token）传递：令牌代表发送权限，以预定义的顺序从一个站传到下一个站。令牌环（token ring）协议中，所有站连成单环结构依次相连，帧也通过此线（令牌总线，token bus）传输。它也无法扩展到较大的网络。

3. 二进制倒计数：由低位至高位比较优先级，信道利用率为 d / ( d + log N )


### 有限竞争协议

* 竞争方法（如ALOHA）：适用于负载较轻的情况
* 无冲突协议：适用于负载较高的情况
* 有限竞争协议（limited-contention protocol）：负载较轻时使用竞争方法，负载较高时使用无冲突协议。

自适应树遍历协议：0号槽允许树根下所有节点尝试获取，如果冲突，则1号槽只允许树根的左子树下所有节点尝试获取，以此类推。


### 无线局域网协议

无线和有线的差异：不能检测正在发生的冲突；传输范围有限，无法和其他站发送/接收帧。

* 隐藏终端问题（hidden station problem）
* 暴露终端问题（exposed station Problem）

冲突避免多路访问（MACA，multiple access with collision avoidance）：发送方刺激接收方输出一个短帧，使其附近的站能检测到该传输。

* RTS（request to send）帧
* CTS（clear to send）帧
（其他站检查帧，可以知道数据帧的长度，从而知道传输所需的时间）

听到RTS帧的站仍能发送，听到CTS帧的站不能发送



## 4.3 以太网

### 经典以太网物理层
### 经典以太网MAC子层协议
### 以太网性能
### 交换式以太网
### 快速以太网
### 千兆以太网
### 万兆以太网
### 以太网回顾


## 4.4 无线局域网
### 802.11体系结构和协议栈
### 802.11物理层
### 802.11MAC子层协议
### 802.11帧结构
### 服务

## 4.5 宽带无线
### 802.16与802.11和3G的比较
### 802.16体系结构与协议栈
### 802.16物理层
### 802.16的MAC子层协议
### 802.16帧结构

## 4.6 蓝牙
### 蓝牙体系结构
### 蓝牙应用
### 蓝牙协议栈
### 蓝牙无线电层
### 蓝牙链路层
### 蓝牙帧结构

## 4.7 RFID（无线射频识别，Radio Frequency IDentification）
### EPC Gen 2 体系结构
### EPC Gen 2 物理层
### EPC Gen 2 标签标识层
### 标签标识消息格式


## 4.8 数据链路层交换

* 网桥（bridge）==交换机
* 路由（router）

### 网桥的使用

* 后向学习算法（backward learning）
* 生成树算法（spanning tree）

### 学习网桥

### 生成树网桥

### 中继器/集线器/网桥/交换机/路由器和网关

### 虚拟局域网（VLAN）


## 4.9 本章总结




# 五、网络层


## 5.2 路由算法

路由算法负责确定一个入境数据包应该被发送到哪条输出线路上。如果网络内部使用了

* 数据报：对每一个到达的数据包重新选择路径，因为上次选择路径后最佳路径可能已经改变。

* 虚电路：只有建立新的虚电路时才需要做路由决策，之后按已建立的路径传递即可。

路由和转发

* 路由：对选择哪条路径做出决策

* 转发：当一个数据包到达时应采取什么动作

路由算法必需的特性：正确性、简单性、鲁棒性、稳定性、公平性、有效性。

路由算法目标：平均延迟最小化？总吞吐量最大化？（折中：降低跳数）

路由算法分类：

* 非自适应算法：静态路由

* 自适应算法：动态路由


### 5.2.1 优化原则

最优化原则：如果路由器J在从路由器I到路由器K的最优路径上，那么从J到K的最优路径也必定遵循同样的路由。

汇集树（sink tree）：以目标节点为根的树。（不唯一，也可以是一个有向无环图）


### 5.2.2 最短路径算法

路径长度测量方法：跳数、地理距离、平均延迟、带宽、平均流量、通讯成本等

Dijkstra算法（全局、理想）


### 5.2.3 泛洪算法

每个路由器必须根据本地知识而不是网络全貌做决策。

跳计数器：每经过一跳计数器减一。理想情况下，跳计数器的初始值应该等于从源端到接收方之间路径的长度。如果发送方不知道该路径有多长，可以初始化为最坏情况，即网络的直径。

随跳数指数增长的重复数据包：让路由器跟踪已经泛洪过的数据包，从而避免二次发送。每个源路由器在接收来自主机的数据包时填上序号，然后每个路由器为每个源路由器准备一张表，记录已经观察到的来自源路由器的序号。

计数器k：表示直到k的所有序号都已经观察到了（防止表无限膨胀）。


### 5.2.4 距离矢量算法

距离矢量路由（distance vector routing）：每个路由器维护一张表，表中列出当前已知的到每个目标的最佳距离，以及所使用的链路。这些表通过和邻居之间相互交换信息而不断被更新，最终每个路由器都了解到每个目的地的最佳链路。

无穷计算问题：好消息传得快，坏消息传得慢。


### 5.2.5 链路状态路由

链路状态路由：

1. 发现它的邻居节点，并了解其网络地址
2. 设置到每个邻居节点的距离或者成本度量值
3. 构造一个包含所有刚刚获知的链路信息包
4. 将这个包发送给所有其他的路由器，并接收来自所有其他路由器的信息包
5. 计算出到每个其他路由器的最短路径

**发现邻居**

1. 路由器在每一条点到点线路上发送一个特殊的HELLO数据包
2. 另一端的路由器返回一个应答说明自己是谁（全局唯一的名字）

**设置链路成本**

链路带宽反比，或链路延迟（一个要求对方立即发回的ECHO数据包，测量往返时间再除2）

**构造链路状态包**

链路数据包格式：

发送方标识符 + 序号（Seq） + 年龄（Age） + 邻居列表

构造数据包的时间：

* 周期性
* 发生重要事情时（断线、停机、恢复等）

**分发链路状态包**

* 序号绕回
* 路由崩溃
* 位错误

解决方案：32位序号，序号后增加年龄字段，每秒年龄减1，年龄为0时，该信息将被丢弃

保留区：一个链路状态数据包被泛洪到一个路由器时，没有立即排入队列等待传输，而是先放到保留区等待一段时间，和新数据包比较后再处理。

**计算新路由**

本地运行Dijkstra算法

需要更多的内存和计算，但没有慢收敛的问题

* IS-IS（Intermediate System - Intermediate System）：应用于IP协议
* OSPF（Open Shortest Path First）

主要差别：IS-IS可同时携带多个网络层协议的信息。

路由算法依赖于所有路由器计算路径的处理，少数路由器的问题都可以肆虐破坏网络。（如一个路由器声称有一条不存在的链路，或忘记一条存在的链路。这种失败的概率在大型网络中是不可忽略的）


### 层次路由

路由器 < 区域（region） < 簇（cluster） < 区（zone） < 群（group）

增长路径长度以节省空间。

N个路由器的网络，最优层数十lnN，每个路由所需表项为elnN。


### 广播路由

* 每个目标单独发送：浪费带宽，要求源机器拥有目标机器完整地址列表。
* 多目标路由（multidestination routing）：数据包携带目标地址（或位图），由路由器检查、复制、发送到必要的线路。
* 逆向路径转发（reverse path forwarding）：包到达路由器时，检查到来的线路是否为最优线路，是则继续转发，不是则丢弃。
* 以发起广播的路由器为根的生成树：要求每个路由都知道这棵生成树。


### 组播路由

* 密集分布：修剪广播生成树
	* 链接状态路由算法：每个路由器对每个发送者自己构造修剪生成树（组播，MOSPF，Multicast OSPF）
	* 距离矢量路由算法：逆向路径转发，PRUNE消息（距离矢量组播路由协议，DVMRP，Distance Vector Multicast Routing Protocol）
* 稀疏分布：基于核心树（core-based trees）
	* 所有路由器都同意某个路由器（核心：core 或 会聚点：rendezvous point）作为根（协议独立组播，PIM，Protocol Independent Multicast）
	

### 选播（Anycast）路由

使用组地址而不是独立地址，算法仍然是距离矢量或链路状态算法。


### 移动主机路由

* 重新计算路由：高负荷。
* 网络层之上提供移动（笔记本）：新的位置获取新的网络地址，新老地址之间不存在任何关联。
* 家乡代理（home agent）（Internet和蜂窝网络）：
	1. 注册转交地址（care of address）
	2. 发送者往家乡地址发送数据包
	3. 隧道（tunneling）到转交地址
	4. 应答发送者
	
需考虑安全性


### 自组织（Ad hoc）网络路由

路由器本身是移动的（地震、战争、舰船、没有WiFi的地方）

Ad hoc按需距离矢量（AODV，Ad hoc Ondemand Distance Vector）路由算法：
* 路由发现：按需发现（只有要发送包时才去找路径）
	1. 源机器广播路由请求（ROUTE REQUEST）包
	2. 目标机器单播路由应答（ROUTE REPLY）包
	3. 在大型网络中，设置TTL（time to live）字段来限制广播范围
* 路由维护：周期性广播HELLO消息

多条路由可以共享

其他Ad hoc路由方案：
* 动态源路由（DSR，Dynamic Source Routing）
* 贪婪边界无状态路由（GPSR，Greedy Perimeter Stateless Routing）



## 5.3 拥塞控制算法

如果路由器拥有无限内存，拥堵情况将是恶化而不是缓解。

* 拥塞控制：全局性（网络能承载所有到达的流量）
* 流量控制：点到点


### 拥塞控制的途径

从慢到快（预防性到反应性）：
* 网络供给（provisioning）
* 流量感知路由（traffic-aware routing）
* 准入控制（admission control）
* 流量限制
* 负载脱落（load shedding）


### 流量感知路由

* 多路径路由
* 流量缓慢迁移


### 准入控制

除非网络可以携带额外的流量而不会变得拥塞，否则不再建立新的虚电路。

流量呈现突发性，往往用其速度和形状来描述。

两个描述符：
* 漏桶（leaky bucket）
* 令牌桶（token bucket）


### 流量调节

衡量路由器拥塞程度：平均利用率没有考虑流量的突发性，而丢包数量计数来得太迟，因此路由器内缓冲排队数据包是最有用的。

指数加权移动平均（EWMA，Exponentially Weighted Moving Average）：排队延迟估计d，瞬间队列长度s，则
d_new = a * d_old + (1-a) * s

* 抑制包（choke packet）：路由发送给发送方
* 显式拥塞通知（ECN，Explicit Congestion Notification）：接收方发送给发送方
* 逐跳后压


### 负载脱落

* 葡萄酒策略：旧包比新包好（文件传输）
* 牛奶策略：新包比旧包好（实时媒体流）
（需要发送方的合作）

随机早期检测（RED，Random Early Detection）：对平均队列长度超过某个阈值的链路，随机丢弃一些包。（丢包比抑制包、ECN更容易被主机检测，主机能隐式地调节输出）



## 5.4 服务质量

提供良好服务的简单解决方案：过度配置（overprovisioning）


### 应用需求

服务质量（QoS，Quality of Service）参数：带宽、延迟、抖动（jitter）、丢失。


### 流量整形

流量整形（traffic shaping）：调节进入网络的数据流的平均速率和突发性所采用的技术。

漏桶和令牌桶

多级令牌桶


### 包调度

可预约的潜在资源：带宽、缓冲区、CPU周期

* FIFO：一个（大）流很容易影响到其他流量的性能
* 公平队列（fair queueing）：每个流设置单独队列
* 加权公平队列（WFQ，Weighted Fair Queueing）


### 准入控制


