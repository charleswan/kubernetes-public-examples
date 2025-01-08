# Scheduling Process

**Step 1: Submit Pod**

**Step 2: Kube-ApiServer**

**Step 3: Controllers (WebHooks)**

Validate/Admit

```
Pod
NodeName:
Phase: Pending
```

**Step 4: Kube-Scheduler**

Filter/Score; Bind NodeName;

NodeName: <code><strong>Node1</strong></code>

```
Pod
NodeName: Node1
Phase: Pending
```

**Step 5: Node (Kubelet)**

Phase: <code><strong>Pending</strong></code>

```
Pod
NodeName: Node1
Phase: Running
```

The scheduling process = Placing Pods onto suitable Nodes.

What does "suitable" mean?
1. Meeting the resource requirements of the Pod. (Resources/QoS/Resource Quota)
2. Satisfying the Pod's specific relationship requirements. (PodAffinity/PodAntiAffinity, NodeSelector/NodeAffinity)
3. Complying with the Node's constraint conditions. (Taint/Tolerations)

