## MVVM模型

### 1.什么是MVVM

Model–View–ViewModel(MVVM) 是一个软件架构设计模式，由微软 WPF 和 Silverlight 的架构师 Ken Cooper 和 Ted Peters 开发，是一种简化用户界面的事件驱动编程方式。由 John Gossman（同样也是 WPF 和 Silverlight 的架构师）于2005年在他的博客上发表。

MVVM 源自于经典的 Model–View–Controller（MVC）模式（期间还演化出了 Model-View-Presenter（MVP）模式，可忽略不计）。MVVM 的出现促进了 GUI 前端开发与后端业务逻辑的分离，极大地提高了前端开发效率。MVVM 的核心是 ViewModel 层，它就像是一个中转站（value converter），负责转换 Model 中的数据对象来让数据变得更容易管理和使用，该层向上与视图层进行双向数据绑定，向下与 Model 层通过接口请求进行数据交互，起呈上启下作用。

![img](https://tva1.sinaimg.cn/large/e6c9d24egy1h2hqgeqh7ej20qu08ndge.jpg)

### 2. Vue中的MVVM设计思想

![image-20220522181651855](https://tva1.sinaimg.cn/large/e6c9d24egy1h2hcmougmrj20v60fmaas.jpg)

- M（Model）表示是模型，或者代表数据
- V（View）表示是视图，视图是用户看到的页面结构和外观
- VM（ViewModel）表示的是视图模型，它是视图的一种抽象形式，在Vue中表示的的是Vue实例

![image-20220522190545778](https://tva1.sinaimg.cn/large/e6c9d24egy1h2he1l1uksj21660u0gpz.jpg)

### 参考

- https://www.liaoxuefeng.com/wiki/1022910821149312/1108898947791072
- https://www.cnblogs.com/Renyi-Fan/p/9907188.html#_label3