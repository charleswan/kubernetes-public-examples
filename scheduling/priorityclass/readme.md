To mark a Pod as critical, set `priorityClassName` for that Pod to `system-cluster-critical` or `system-node-critical`. 

`system-node-critical` is the highest available priority, even higher than `system-cluster-critical`.

Some built-in priorities:
- Built-in priority: `DefaultPriorityWhenNoDefaultClassExists=0`
- User-configurable maximum priority limit: `HighestUserDefinablePriority=1000000000`
- System-level priority: `SystemCriticalPriority=2000000000`
- Built-in system-level priority: 
    - `system-cluster-critical`
    - `system-node-critical`

Priority Preemption Strategy:
- podEligibleToPreemptOthers -> nodesWherePreemptionMightHelp -> selectNodesForPreemption -> processPreemptionWithExtenders -> pickOneNodeForPreemption -> DeletePod

Preemption Node Selection Strategy:
- First, choose the node that breaks the PDB (Pod Disruption Budget) the least.
- Next, select the node with the lowest priority among the preempting Pods.
- Then, choose the node with the smallest sum of preempting Pods' priorities.
- After that, choose the node with the fewest preempting Pods.
- Finally, select the node with the latest started Pod.
