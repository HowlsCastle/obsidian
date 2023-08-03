what：
informer 是k8s API客户端的一个库，用于监控k8s中资源变化。可以实时获取到资源变化，如增删改等操作，将变化通知给应用。

why：
使用了k8s的 `watch API`监控k8s中资源变化，并将变化转化为事件，并将事件发送给应用程序，ying'yong

how：
可以使用informer做缓存、索引、筛选