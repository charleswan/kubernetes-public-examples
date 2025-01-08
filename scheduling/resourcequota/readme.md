# Resource Quotas

https://kubernetes.io/docs/concepts/policy/resource-quotas/

Limit the resource usage for each Namespace.

Usage:
- Per Namespace.
- Scope:
    - Terminating/NotTerminating
    - BestEffort/NotBestEffort
    - PriorityClass
    - CrossNamespacePodAffinity

`quota.yml`:
Limit the quota for non-BestEffort QoS in the demo-ns Namespace:  
- CPU can only use 1000 cores  
- Memory can only use 200Gi  
- Only 10 Pods can be created
