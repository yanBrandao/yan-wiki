# Kubernetes Questions

### Kubernetes

`Q: Handler Implementation in Kubernetes`
 
In Kubernetes, a Handler is a part of the Lifecycle configuration of a Pod, defining actions that should occur in response to specific lifecycle events of a container. Kubernetes uses Handlers to allow you to hook into certain stages of the container's lifecycle.

Handlers are typically associated with the following lifecycle hooks:

*PostStart*: Invoked immediately after a container starts.
*PreStop*: Invoked immediately before a container is terminated.

With a handler is possible to:
 - Execute an Action
 - Make a httpGet request

**Best Practices**

_Keep it lightweight_: Avoid complex, long-running logic. If the postStart hook takes too long, it can delay the readiness of your container.
_Error handling_: Ensure proper error handling, as failures in postStart hooks may result in Pod failures.
_Testing_: Test your postStart logic thoroughly in staging environments to ensure it doesn't introduce startup delays or instability.

References: 
- https://kubernetes.io/docs/tasks/configure-pod-container/attach-handler-lifecycle-event/
- https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#container-hooks

`Q:Which probe should we use to make sure that no requests go to the POD`

To ensure that no requests are sent to a Pod until it is fully ready to serve traffic, you should use the _Readiness Probe_ in Kubernetes. The Readiness Probe determines whether a container is ready to handle incoming traffic.


| Probe | Purpose |
| --- | --- |
| Readiness Probe | Ensure that the container is ready to handle incoming traffic. |
| Liveness Probe | Ensure that the container is still running and healthy. |
| Startup Probe | Ensure that the container is ready to handle incoming traffic after it has started. |

Reference: 
 - https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/
