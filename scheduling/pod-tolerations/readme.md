`effect` (Can be empty which means match everything):
- `NoSchedule`: It only prevents new Pods from being scheduled.
- `PreferNoSchedule`: The goal is to avoid scheduling on this node.
- `NoExecute`: It will evict Pods that don't have the corresponding toleration and will not schedule new ones.

Operator: `Exists`/`Equal`

The Pod must have Tolerations with `k1=v1` and a `NoSchedule` effect.