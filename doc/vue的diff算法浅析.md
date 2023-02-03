首先为什么会存在diff算法呢？

提到diff算法，就要提及到vue中的双向绑定的实现，双向绑定的原理是把数据模型绑定到视图中，视图也就是用户所能看到的UI界面。对于开发者来说也就是vue最终生成的html文件。因此数据的更新，会直接影响html的生成，对于js来说就是控制dom作出一系列的操作，如新增，修改，删除。

在vue中有Virtual DOM这个概念（可能其他框架/库也有），他把真实的DOM树用虚拟的DOM进行描述，优化了当数据模型变更时UI界面的更新，为了高效地完成这个动作，vue中使用diff算法进行新老VDOM的比对。

从vue的源码入手，分析diff的算法




参考：
[极为细致的Vue的Diff流程详解——以流程图表达](https://segmentfault.com/a/1190000038894967)
[Vue2 VS Vue3 Diff算法的比较](https://www.naoffer.com/article/detail/5015)