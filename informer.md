what：
informer 是k8s API客户端的一个库，用于监控k8s中资源变化。可以实时获取到资源变化，如增删改等操作，将变化通知给应用。

why：
使用了k8s的 `watch API`监控k8s中资源变化，并将变化转化为事件，并将事件发送给应用程序，应用程序通过注册事件处理程序，来处理发送过来的事件

how：
可以使用informer做缓存、索引、筛选


```
Informer, InformerFactory, err := node.NewNodeInformer(c.ClusterConfig)  
if err != nil {  
   return  
}  
Informer.Informer().AddEventHandler(cache.ResourceEventHandlerFuncs{  
   AddFunc: func(obj interface{}) {  
        
   },  
   UpdateFunc: func(oldObj, newObj interface{}) {  
        
   },  
   DeleteFunc: func(obj interface{}) {  
        
   },  
})


// 生成controller
lw := cache.ListWatch{  
   ListFunc: func(options v1.ListOptions) (runtime.Object, error) {  
   },  
   WatchFunc: func(options v1.ListOptions) (watch.Interface, error) {  
  
   },  
}  
store, controller := cache.NewInformer(c.ClusterConfig, &v1beta12.Ingress{}, time.Second*30, cache.ResourceEventHandlerFuncs{  
   AddFunc: func(obj interface{}) {  
  
   },  
   UpdateFunc: func(oldObj, newObj interface{}) {  
  
   },  
   DeleteFunc: func(obj interface{}) {  
  
   },  
})

```

webhook
提供资源初始化和验证能力
MutatingWebhook和ValidatingWebhook