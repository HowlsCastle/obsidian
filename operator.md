#
I：
scheme：
```
import (
    "k8s.io/apimachinery/pkg/runtime"  
    utilruntime "k8s.io/apimachinery/pkg/util/runtime"
)
var scheme   = runtime.NewScheme()

func init() {
	utilruntime.Must()
}

```

