#
I：
scheme：
```
// 创建一个新的Scheme对象，并将client-go库中的Kubernetes API对象类型注册到Scheme中
import (
    "k8s.io/apimachinery/pkg/runtime"  
    utilruntime "k8s.io/apimachinery/pkg/util/runtime"
    clientgoscheme "k8s.io/client-go/kubernetes/scheme"
)
var scheme   = runtime.NewScheme()

func init() {
	utilruntime.Must(clientgoscheme.addToScheme(scheme))
}

```
可以使用scheme对象进行序列化和反序列化

runtime.schemeBuilder:

