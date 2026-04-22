What a pod is?
- A deployable unit in k8s that consists of service clusters.

What a deployment does?
- It defines a desired state, and k8s ensures that it matches this with automated scaling, rolling updates and self-healing.

What a service does?
- It is an API object that enables network exposure for one or more cluster Pods. (Load Balancer)

What happened when you deleted a pod?
- It auto-healed immediately after as k8s will always aim to be in the desired state declared in the deployment.