# Concepts #

* Job: A job can contain multiple tasks, which is the basic unit of system management and the basic unit for user creation and deletion.
 
* Task：A task is the basic unit of system scheduling. Queuing and execution are performed on a task-by-task basis. A task runs on a virtual cluster (vcuster), and the nodes of the cluster are called virtual nodes (vnodes).

* Vnode：A task can run on multiple vnodes, and a vnode corresponds to a container runtime that encapsulates the runtime environment and resources. All vnodes of a task have the same resource configuration and mirroring.