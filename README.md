This code is for a scheduling method based on place-timed Petri nets (PNs) and an A* search algorithm. To alleviate the computational burden of scheduling robotic cellular manufacturing (RCM) systems modeled by PNs, existing methods have primarily focused on designing more informed heuristic functions or relaxing the search at the expense of optimality. Different from that, this paper proposes an A∗ search enhanced with PN-treaps, which accelerates the search process by efficiently storing and managing large state lists, such as OPEN and CLOSED, that are commonly encountered in PN-based A∗ search.

本程序平台采用C#实现我们所提出的基于Petri网的类A*搜索算法，详细算法描述请参见我们的英文专著及相应论文。

Bo Huang, MengChu Zhou. Supervisory Control and Scheduling of Resource Allocation Systems. Hoboken, NJ, USA: John Wiley & Sons (IEEE-Wiley), July 2020.

Bo Huang, MengChu Zhou, XiaoYu Sean Lu, and Abdullah Abusorrah. Scheduling of Resource Allocation Systems with Timed Petri Nets: A Survey. ACM Computing Surveys, Feb. 2023, 55(11): 1-27.

本平台基于Visual Studio 2008开发，安装VS2008后直接双击后缀名为.sln或.csproj文件即可打开运行。如果采用的不同版本的VS则可能无法直接打开，此时需要新建空白C# Console工程，将Main.cs, AStar.cs, Heap.cs, Treap.cs和TreapBase.cs五个文件，以及bin文件夹和帮助文档拷贝至新建工程的所在目录，然后在工程中Project->add existing item将五个cs文件加入即可。（将老的程序备份，并创建新的程序也是此流程）

运行：打开main.cs，点击Debug->Start Debugging(F5)

平台组成：

Main.cs: 主程序，输入一些用户参数。

AStar.cs: 搜索程序，定义了两个类AStarNode和AStar。

Heap.cs: 堆栈操作函数，用于处理OPEN, CLOSED之类的堆栈操作，通常不用改动，直接调用即可。

Treap.cs: 树堆操作函数，用于处理OPEN， CLOSED之类的树堆操作，通常不用改动，直接调用即可。

TreapBase.cs: 树堆节点所含链表操作函数，用于处理具有相同marking值的不同状态，通常不用改动，直接调用即可。

Bin/Debug文件夹：存放输入和输出文件。输入文件，对于一个Petri网，需要给出两个输入文件，其中xxx_matrix.txt放置Petri网的关联矩阵的转置矩阵（即行为变迁，列为托肯），xxx_init.txt放置起始标识，库所操作时间信息，和目的标识。输出文件为0result.txt。

版本更新说明：

https://static.app.yinxiang.com/embedded-web/profile/#/join?guid=0f885707-2f1a-4ea6-9fab-f2479b6dd6b5&sharedNotebookGuid=&channel=copylink&shardId=s34&ownerId=25641086

For any inquiries or issues, please reach out to us at huangbo@njust.edu.cn.

November 23, 2025.
