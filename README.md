# WanKeYunApi

玩客云远程下载API。抄 github.com/Immortalt/imt-wanke-client 的API，并且做了最新的兼容

## 目的

方便追美剧、动漫，也就是自动下载。

## 细节

* 这个玩意可以下载的东西就跟迅雷下载东西一样，填写对应的下载信息，丢进去即可
* 可以指定 下载的路径，前面的盘符会在下面的代码补上去。但是提交一次只能指定一次下载目录

> 这个目录不存在的话，它会自动新建，区分大小写
>
> defaultPath = "/onecloud/tddownload"
>
> 盘符怎么补上去的，看 OneThingHelper  的代码，目前个人只有一个硬盘所以就默认第一个磁盘。

* 下载示例看 OneThingHelper 最下面
* 具体的调用 API 看这个 APIHelper_OneThing
* 看具体下载任务返回值的时候，你会发现其实下载任务没有离线通道的权限，也没得 VIP 通道的权限，至少返回值是这么提示的
* 目前在家监控网络流量来看，你下载的电影是不会默认上传的，也许后面会

## PS

原作者没有做远程磁盘文件枚举。自己也尝试抓包分析，可惜，新接触这些搞不懂。

所以现在并不能很好的去管理远程磁盘中的文件，当然，可以曲线救国

* 玩客云开启 SMB 共享
* 树莓派连接共享目录，进行磁盘文件的统计管理，然后再调用下载逻辑

希望有人能指导下抓包分析玩客云通信，解决远程磁盘文件枚举问题

或者你搞定了欢迎推送上来分享

## 感谢

感谢原作者 github.com/Immortalt/imt-wanke-client 的开源。

