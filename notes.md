What a pod is?
- A deployable unit in k8s that consists of service clusters.
Pods are ephemeral
Deployments are the declarative source of truth

What a deployment does?
- It defines a desired state, and k8s ensures that it matches this with automated scaling, rolling updates and self-healing.

What a service does?
- It is an API object that enables network exposure for one or more cluster Pods. (Load Balancer)

Service has a selector (labels)
It dynamically tracks matching pods
It updates endpoints automatically

A Kubernetes Service is a stable network abstraction that routes traffic to a dynamic set of pods selected via labels, ensuring consistent access despite pod lifecycle changes.

What happened when you deleted a pod?
- It auto-healed immediately after as k8s will always aim to be in the desired state declared in the deployment.
Deployment controller continuously reconciles actual state vs desired state

What happens when you set an incorrect image?
- ImagePullBackOff / ErrImagePull
It keeps trying because the desired state is still replica=1

What happens if labels are wrong?
- Service selector mismatch
Service cannot find pods
Endpoints list becomes empty
Traffic goes nowhere (timeout / connection refused)

What is the difference between Pod IP and Service IP?
-
Pod IP: 
Assigned per pod
Ephemeral (changes when pod is recreated)
Not stable for communication

Service IP:
Stable virtual IP inside cluster
Does NOT belong to a container
Represents a load-balanced endpoint abstraction
