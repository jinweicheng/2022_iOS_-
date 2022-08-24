# 2022_iOS_Interview

### 1-1、http/https
HTTP是什么？: http是规范二点之间传输文本、图片、音频、视频等的协议（超文本传输协议）；
	HTTP 通常跑在 TCP/IP 协议栈之上，依靠 IP 协议实现寻址和路由、TCP 协议实现可靠数据传输、DNS 协议实现域名查找、SSL/TLS 协议实现安全通信。
	CDN，全称是“Content Delivery Network”，翻译过来就是“内容分发网络”。它应用了 HTTP 协议里的缓存和代理技术，代替源站响应客户端的请求。
	WAF 是近几年比较“火”的一个词，意思是“网络应用防火墙”。与硬件“防火墙”类似，它是应用层面的“防火墙”，专门检测 HTTP 流量，是防护 Web 应用的安全技术。
	DNS域名系统（Domain Name System）。
	URI（Uniform Resource Identifier），中文名称是 统一资源标识符，使用它就能够唯一地标记互联网上资源。
	HTTPS 就相当于这个比喻中的“火星文”，它的全称是HTTP over SSL/TLS
	TCP/IP 协议是目前网络世界“事实上”的标准通信协议。
	TCP/IP 协议总共有四层：
		第一层叫“链接层”（link layer），负责在以太网、WiFi 这样的底层网络上发送原始数据包，工作在网卡这个层次，使用 MAC 地址来标记网络上的设备，所以有时候也叫 MAC 层；
		第二层叫“网际层”或者“网络互连层”（internet layer），IP 协议就处在这一层；
		第三层叫“传输层”（transport layer），这个层次协议的职责是保证数据在 IP 地址标记的两点之间“可靠”地传输；
		第四层叫“应用层”（application layer），由于下面的三层把基础打得非常好，所以在这一层就“百花齐放”了，有各种面向具体应用的协议。例如 Telnet、SSH、FTP、SMTP 等等，当然还有我们的 HTTP
	OSI 网络分层模型：物理层、链接层、网际层、传输层、会话层、表示层、应用层
	
为什么需要三次握手和四次分手？

### 1-2、
    Weak的实现原理(https://juejin.cn/post/6844904101839372295 )  unsafe_unretain区别
    组件化了解： https://blog.51cto.com/mlcmlc/4900253 
    数组和链表区别，反转链表（https://www.developers.pub/article/1070720 ）
    排序算法: 快排 https://www.cnblogs.com/MOBIN/p/4681369.html 
    找两个view的最近父视图