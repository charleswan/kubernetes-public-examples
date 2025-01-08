`effect` (Cannot be empty):
- `NoSchedule`: It only prevents new Pods from being scheduled.
- `PreferNoSchedule`: The goal is to avoid scheduling on this node.
- `NoExecute`: It will evict Pods that don't have the corresponding toleration and will not schedule new ones.

The Node has Taints with `k1=v1` and a `NoSchedule` effect.
