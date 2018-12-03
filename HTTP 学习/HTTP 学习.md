
### HTTP 学习

>HTTP协议：Hyper Text Transfer Protocol（超文本传输协议）
>**TCP/IP:Transmission Control Protocol/Internet Protocol**(传输控制协议/因特网互联协议)

>万维网：WWW:World Wide Web 

>Web框架：Web framework

应用层
>FTP：File Fransfer Protocol （ 文件传输协议 ）
>DNS：Domain Name System (域名系统）

传输层
>TCP:Transmission Control Protocol（传输控制协议）
>UDP:User Data Protocol (用户数据报协议)

链路层
>NIC:Network Interface Card (网络适配器，即网卡)

**TCP/IP 通信传输过程**
![Alt text](./001.png)
![Alt text](./002.png)


> 发送端在层与层之间传输数据时，每经过一层必定会被打上一个该层所属的首部信息。反之，接收端在层与层传输数据时，每经过一层会把对应的首部消去。

这种把数据信息包装起来的做法叫**封装（encapsulate）**


**IP协议**
IP: Internet Protocl （位于网络层）
>这是说的’IP’不是'IP地址'，而是一中协议的名称。


IP协议的作用是把各种数据包传给对方。
依托两个重要条件：

>IP地址 和 MAC地址（IP地址可变化，MAC 地址基本不会更改）

MAC：Media Access Control Address  

使用ARP协议 凭借MAC地址进行通信
ARP协议：Address Resolution Protocol
>IP间的通信依赖MAC地址。在网络上，通信的双方在同一局域网（LAN）内的情况是很少的，通常是经过多台计算机和网络设备中转来连接对方。
>ARP是一种用于解析地址的协议，根据通信方的IP地址就可以反查出对方对应的MAC地址。
![Alt text](./003.png)


**确保可靠性的TCP协议**
TCP位于传输层，采用三次握手策略。
>用TCP 协议把数据包发送出去后，TCP不会对传送后的情况置之不理，它一定会向对方确认是否成功到达。

![Alt text](./004.png)

