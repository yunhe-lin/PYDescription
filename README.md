##PYDescription
如何维护自身的pod库（仿造cocoapods）

<ol>
<li>cocoaPods</li>
<li>添加pod</li>
<li>cocoaPods 实现管理pod 原理</li>
<li>搭建自己项目的cocoaPod管理平台</li>
<ol>
#--
>cocoaPods

>>开发 iOS 项目不可避免地要使用第三方开源库，CocoaPods 的出现使得我们可以节省设置和更新第三方开源库的时间。这个就不多做解释了。

>添加pod

>>简略的说：
</br>
需要一个合法经过校验的源代码pod库, 创建pod库 "PYUtil" ，修改PYUTil.podSpec文件，校验PYUTil，通过后就能上传到自己的远端代码仓库中。然后修改podfile中添加你的 pod 'podName', :git => 'url' 类似与这样的形式.
[学习如何生成pod库模板](http://www.cnblogs.com/brycezhang/p/4117180.html)(带上如何静态库连接，学习后会带上静态库的pod管理).

>>如果只是想简单引入自身维护的单个pod库的话，那么到这里你已经可以结束了。
>>
>>简单阐述一下为什么需要维护自身项目的pod的管理平台。大致上pod维护分为两种，一种基础公共的pod库和业务pod库。维护pod管理平台的好处最大的得意者是业务库。一次版本的迭代跨越一个大版本。例如从0.1.0 -> 0.2.0，开发过程中小版本的跨越。如此一来以往版本的带麻将bug只需切换分支就显而易见。
>
cocoaPods 实现管理pod 原理

>>
![icon]()