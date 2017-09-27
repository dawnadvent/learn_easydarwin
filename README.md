# learn_easydarwin_
学习EasyDarwin流媒体视频平台框架

一、RTSP  Real Time Streaming Protocal  实时流媒体协议
1、是TCP / IP协议中的一个应用层协议，适用于C / S模型，使用TCP / UDP完成数据传输，与HTTP的请求都是由客户端发出的规则有所不同，RSTP协议是双向的，RSTP是用来控制声音或影像的多媒体串流协议，并允许同时多个串流需求控制，不特别强调时间同步，所以比较能容忍网络延迟，具有重新导向功能，因此可视实际的负载情况来转换提供服务的服务器，以避免过大的负载集中于某个服务器而导致更大的网络延迟。
2、一个基于文本的协议，用于在C/S之间建立和协商实时流会话。
3、协议特点：
  1）可扩展性：新方法和参数很容易加入RTSP
  2）易解析：RTSP可由标准HTTP或MIME解析器解析
  3）安全：RTSP使用网页安全机制
  4）独立于传输：RTSP可使用不可靠数据报协议（EDP)、可靠数据报协议（RDP);
  5）多服务器支持：每个流可放在不同服务器上，用户端自动与不同服务器建立几个并发控制连接，媒体同步在传输层执行；
  6）记录设备控制：协议可控制记录和回放设备
  7）流控与会议开始分离：仅要求会议初始化协议提供，或可用来创建唯一会议标识号。特火速情况下，可用SIP或H.323来邀请服务器入会
  8）适合专业应用：通过SMPTE时标，RTSP支持帧级精度，允许远程数字编辑。
  9）演示描述中立：协议没强加特殊演示或元文件，可传送所用格式类型；然而，演示描述至少必须包括一个RTSP URL。
  10）代理与防火墙友好
  11）HTTP友好，RTSP采用HTTP观念，使现在结构可重用。
  12）适当的服务器控制：如用户启动一个流，必须也可以停止一个流
  13）传输协调：实际处理连续媒体流前，用户可协调传输方法
  14）性能协调：
4、RTSP连接请求传送方式：
  1）持久传输链接，用于多个请求/响应传输
  2）每个请求/响应传输一个连接
  3）无连接模式
5、RTSP操作：
  1）服务器必须以收到请求的同样顺序发出响应。
  2）在TCP中RTT估计的初始值为500ms。应用缓存最后所测量的RTT，作为将来连接的初始值。
  3）实现RTSP的系统必须支持通过TCP传输RTSP，并支持UPD。对UPD和TCP，RTSP服务器的缺省端口都是554.
6）RTSP扩展
  由于不是所有媒体服务器有着相同的功能，媒体服务器有必要支持不同的请求集。RTSP可以如下3种方式扩展：
  1）以新参数扩展。
  2）加入新方法。如信息接收者不理解请求，返回501错误代码，发送者不应再尝试这和总分那个法。
  3）定义新版本协议，允许改变所有部分（协议版本号位置除外）。
7）操作模式
  每个演示和媒体流可用RTSP URL识别。使用HTTP或者其他途径可以获得演示描述定义文件。演示可包含多个媒体流。除媒体参数外，网络目标地址和端口也需要决定。
  下面区分几种操作模式。
  1）单播：有过户选择的端口号将媒体发送到RTSP请求源
  2）服务器选择地址多播：媒体服务器选择多播地址和端口，这是现场直播或准点播常用的方式。
  3）用户选择地址多播：如服务器加入正在进行的多播会议，多播地址、端口和密钥由会议描述给出。
8）微软RTSP协议和标准RTSP协议的区别
  微软的RTSP规范与标准的RTSP协议相比最主要的改动是发送报payloads到客户端的方式，，另外还有一些请求命令有改动。传输单个媒体包的机制并没有文档，这可能是微软要保留的信息。就像MMS和HTTP1.0流协议使用一个媒体数据包头一样，RTSP也有，这导致在企图连接微软的RTSP服务器时，是个主要问题。
