合法的场景：
- namespaced scope owned by the same namespaced scope
- cluster scope owned by cluster scope
- namespaced scope owned by cluster scope
在合法的场景下，一个有效的属主仅校验GVK和UID，错误的名称并不影响回收功能。

不合法的场景：
- namespaced scope owned by the different namespaced scope（在指定这种属主关系时，前者就会被立即回收删除，因此这种属主关系无法建立成功）
- cluster scope owned by namespaced scope（可以成功建立属主关系，但是这种关系并不会生效，即在namespace scope资源删除时，cluster scope资源不会被删除，这种属主关系不校验属主是否存在，并且会在cluster scope资源上产生OwnerRefInvalidNamespace事件）
