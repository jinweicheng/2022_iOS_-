# 2022_iOS_Interview

## 一、常问的面试题目
### 1-1、iOS事件响应链: <https://juejin.cn/post/6894518925514997767>
### 1-2、Set和字典区别：
    相同点（都是无序的不可重复），不同点（set存储方式是只有键值没有键名，字典是有key和value；字典get和set速度都很快内存占用很大）
### 1-3、数组和链表：
    数组是内存中连续的，链表是内存不连续的，数组的查找时间复杂度O(1),插入和删除的为O(n),链表插入和删除效率较高O(1)，查找效率为O(n)
### 1-4、字典的底层结构：
    字典内部的实现是通过key和value进行实现的，通过map映射实现的，在set的时候通过对key进行运算生成index，去对应的index存储值，get的时候通过key生成index进行取值操作。
### 1-5、内存管理
    UIView Animation :因为self并没有强引用uiview
    Massory/GCD/AFNetworking: 因为 self.obj 强引用block，block并没有对捕获的对象进行强引用
### 1-6、isa和superclass：
    给nsobject和person新增分类：里面实现了实例方法，没有实现类方法，但是我们去调用类方法的结果，nsobject会最终调用实例方法，person直接报错方法找不到
    
### 1-7、Weak的实现原理：
    (https://juejin.cn/post/6844904101839372295 )  unsafe_unretain区别
### 1-8、JS与OC交互
    https://github.com/reborn-developer/WKWebview-MessageHandler 
### 1-9、 CALayer上的button的点击事件： <https://juejin.cn/post/6844903533846724615>
### 1-10、项目优化包、App Tinning瘦身的操作、ipa包和App Store上包的区别
### 1-11、结构体、枚举方法、block的方法的派发方式
### 1-12、class和staic的区别: 都可以修饰类方法，但是static不能继承
### 1-13、swift中的String和oc中的nsstring的区别:
    swift中的String不分可变不可变，都是可变的字符串.通过prefix和suffix得到的为substring.
		oc中的NSSring是引用类型，而swift中的String为值类型.
		swift中的String为为结构体实现，oc中的NSSring为消息发送机制.
		oc的NSSring和 swift中的String可以通过as进行类型转化.
### 1-14、IOS 进程间通信
    <https://juejin.cn/post/7065222370562146335> 
### 1-15、iOS的性能优化
    1、第三方库插桩： <https://cloud.tencent.com/developer/article/1768447>
    2、APP网络优化之DNS优化实践： <https://juejin.cn/post/6844904036294983688>
    3、iOS二进制重排: <http://yulingtianxia.com/blog/2019/09/01/App-Order-Files/ > 
			<https://cloud.tencent.com/developer/article/1814588>  
	 4、ibireme的runloop:<https://blog.ibireme.com/2015/05/18/runloop/> 
	 5、微信的卡顿检测工具: <https://github.com/tencent/matrix/tree/master/matrix/matrix-iOS> 
 	 6、app启动速度优化 <https://mp.weixin.qq.com/s?__biz=MzI1MzYzMjE0MQ==&mid=2247485101&idx=1&sn=abbbb6da1aba37a04047fc210363bcc9&token=2051547505&lang=zh_CN&scene=21#wechat_redirect>  
    7、app开发优化必看： <https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzI1MzYzMjE0MQ==&action=getalbum&album_id=1590407423234719749&scene=173&from_msgid=2247485101&from_itemidx=1&count=3&nolastread=1#wechat_redirect>  
    
    
## 二、OC与swift
### 2-1、Swift的功能更加强大
      1、功能更加强大:switch case支持Character、String类型,oc语言只支持整型!
	 	2、Oc的枚举本质就是整型、swift的枚举可以关联值绑定/枚举的原始值设置.
  		3、for循环、switch中使用where条件过滤.
  		4、可选项绑定 if let name = person?.name 
  		5、lazy延迟存储属性（不是线程安全的），let的变量必须在初始化之前有值。
  		6、函数的参数标签:提升的func的代码的可读性和功能强大。
  		7、swift的泛型，可以将函数的类型参数化，使得函数的功能更加强大。
		8、非空  （let name，_?）或者let value?
    swift更加功能强大：switch case支持更多类型，函数的标签参数,函数的可变参数，swift的面向协议编程。
		
### 2-2、Swift的安全特性:
      1、便捷初始化器、required指定初始化（可以完整的初始化实例）、反初始化器deinit保证swift的安全性
	 	2、switch需要处理所有情况，要不就报错！
  		3、可选项Optional, 空和运算符??，guard关键字，swift可选链person?.name。
  		4、lazy延迟存储属性（不是线程安全的），let的变量必须在初始化之前有值。
  		5、Error Try配合do catch使用  defer保证不管是throw还是return方式返回的代码，defer的代码在作用域结束之前都会执行.

	swift语言更加安全:体现在访问控制open、public等字段,初始化器的赋值机制（可以完整地初始化所有实例：初始化存储属性，定制实例），optional机制,guard机制。
	
### 2-3、Swift开发中的小技巧:
     在debug模式下使用assert(value != 2,”value不等于2错误”)，realse下可以忽略此代码
		在swift中class可以使用关联对象
		defer关键字（在延迟资源回收之前执行方法）的使用：在加锁和解锁的代码中非常有用 
### 2-4、Swift中枚举、结构体、类注意事项:
      1、mutating的枚举和结构体。
		2、final修饰的下标、方法禁止被重写！
		3、swift的extention，不能添加存储属性(影响内存结构)，不能添加覆盖原有的功能,不能新增父类(影响内存结构)，不能新增指定初始化器和反初始化器.
		4、extension可以为协议扩展方法,extension可以为协议扩展方法，间接也实现了协议中方法的必须实现的可选协议效果！！！！
		5、lazy延迟存储属性（不是线程安全的），let的变量必须在初始化之前有值
		
### 2-5、Swift的本质研究:
      1、可选项的本质为:关联的enum类型，none、some。
 		2、inout的本质就是引用传递,计算属性的inout本质先调get方法，test方法，set方法。
		3、Oc的枚举本质就是整型、swift的枚举可以关联值绑定。枚举的rawvalue的本质只读计算属性。
### 2-6、Swift的函数式编程:
    定义：函数式编程Functional Programming,简称FP是一种编程范式（把计算过程尽量分解成一系列可复用函数的调用）。
		引用场景:map、flatmap、reduce、fliter等等…
		优势：提升代码可读性，增加 代码的复用性。
		flatmap和map的区别: <https://blog.devtang.com/2016/03/05/swift-gym-4-map-and-flatmap/>
### 2-7、Swift的面向协议编程:
      swift的面向协议编程POP(Protocol Oriented Programming)，优先考虑协议，面向协议结构体、枚举和类都可以使用
		面向对象编程OOP(Object Oriented Programming)，优先考虑继承
		
		定义:POP就是通过协议扩展，协议继承和协议组合的方式来设计需要编写的代码。
		场景:swift中枚举和结构体是值类型，不适合更加适合面向对象继承的代码实现；在不同的代码继承环路中，根据solid原则继承会增加代码的冗余和单一指责	不清楚的问题。
		优势:协议的好处就是能够做到接口隔离，单一职责化，降低偶合度，减少代码冗余和提升可读性。
		设计模式角度:继承有很大的问题，根据里式替换原则，子类是不能够重写父类的方法的，要不然会破会父类的完整性。
		面向协议参考: <https://juejin.cn/post/6844903928446844935> 	
### 2-8、Swift的响应式编程:
      定义:Reactive Programming简称RP，是一种编程范式。一般是和函数式融合在一起使用，所以常叫函数式响应式编程。
		场景:ReactiveCocoa简称RAC、ReactiveX简称RxSwift(参考：<https://reactivex.io/languages.html> ,中文地址: <https://beeth0ven.github.io/RxSwift-Chinese-Documentation/> )
		优势:可以简化异步编程、提供更优雅的数据绑定。平时开发中的数据绑定，状态监听代码的耦合性较高，错综复杂的依赖关系.
		
## 三、组件化 
    组件化了解： <https://blog.51cto.com/mlcmlc/4900253>
    组件化通讯：组件和组件之间如何通讯
    组件化新版本和旧版本sdwebimage: https://www.jianshu.com/p/63a9a20256de 
    一个组件中的一个文件被其他二个组件使用，怎么优化： subModule方式 

## 四、代码规范与架构
### 4-1、SOLID原则: <https://www.cnblogs.com/suli0827/p/9515842.html> 
AOP(面向切面编程)  是OOP的延续
### 4-2、代码规范：<https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CodingGuidelines/CodingGuidelines.html>
### 4-3、架构
    <https://medium.com/ios-os-x-development/ios-architecture-patterns-ecba4c38de52>
	MVC、MVVM架构：<https://casatwy.com/iosying-yong-jia-gou-tan-viewceng-de-zu-zhi-he-diao-yong-fang-an.html>
	MVP架构：<https://juejin.cn/post/6964252878726758407> 
	VIPER架构: <https://www.objc.io/issues/13-architecture/viper/  或者 https://objccn.io/issue-13-5/> 
	
	
## 五、http/https
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
	
为什么需要三次握手和四次分手？ <https://www.cnblogs.com/Courage129/p/14324605.html>

## 六、技术文章

### 6-1、美团: <https://tech.meituan.com/2021/02/25/cocoapods-hmap-prebuilt.html> 
### 6-2、头条: <https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzI1MzYzMjE0MQ==&action=getalbum&album_id=1590407423234719749&scene=173&from_msgid=2247485101&from_itemidx=1&count=3&nolastread=1#wechat_redirect> 
### 6-3、极客: <https://time.geekbang.org/column/article/85326 >
### 6-4、喵神: <https://kemchenj.github.io/> 
### 6-5、戴铭: <https://ming1016.github.io/categories/Programming/>   
		 <https://github.com/ming1016>
### 6-6、孙源runloop: <https://v.youku.com/v_show/id_XODgxODkzODI0.html> 
### 6-7、官方的runloop: <https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/Multithreading/RunLoopManagement/RunLoopManagement.html>  
### 6-8、招聘一个靠谱的iOS 开发： <https://github.com/ChenYilong/iOSInterviewQuestions/blob/master/01%E3%80%8A%E6%8B%9B%E8%81%98%E4%B8%80%E4%B8%AA%E9%9D%A0%E8%B0%B1%E7%9A%84iOS%E3%80%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88/%E3%80%8A%E6%8B%9B%E8%81%98%E4%B8%80%E4%B8%AA%E9%9D%A0%E8%B0%B1%E7%9A%84iOS%E3%80%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88%EF%BC%88%E4%B8%8B%EF%BC%89.md> 

       	      
## 七、算法:
### 7-1、排序算法: 快排 <https://www.cnblogs.com/MOBIN/p/4681369.html> 
### 7-2、找两个view的最近父视图
### 7-3、链表反转 https://www.developers.pub/article/1070720  中间链表
### 7-4、爬楼梯：100节楼梯



    
