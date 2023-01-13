1. 模板方法     针对方法中的通用逻辑我们可以定义私有的方法自行实现，例如状态的转换和事件监听的处理我们可以定义了 setStateInternal 方法，
               而非通用逻辑定义相应的抽象方法交给具体子类去实现
    例如：
       LifecycleBase.initInternal()
       LifecycleBase.startInternal()
       LifecycleBase.stopInternal()
       ...

       子类进行实现
       StandardService
       Connector
       AbstractHttp11Protocol
       ...

2. 组合模式     组件层级调用 init() 方法和 start() 方法
    例如：
        Service.init()
        Connector.init()
        ProtocolHandler.init()
        ...

        Service.start()
        Connector.start()
        ProtocolHandler.start()
        ...

3. 观察者模式        把组件的生命周期定义成相应的状态，把状态的转变看作是一个事件。
                   有了事件就需要有监听器，在监听器里可以实现一些内部逻辑，并且监听器也可以方便的添加和删除
    例如：
        LifecycleBase.init()
        LifecycleBase.start()
        ...

4. 适配器模式
    例如：
        protocolHandler.setAdapter(adapter)