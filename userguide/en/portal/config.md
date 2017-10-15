## Config ##


Users will configure their Workspace here, mainly the management of
vclusters and images.

The following picture shows the Config webpage of **tee** Workspace:

<img src="../images/config-workspace.png" width="600" alt="workspace
config">

### Scale in/out

Users can add nodes to or remove nodes from the vcluster. The above
picture show the *tee* Workspace having two nodes, with the detailed
information about node's name, IP address, status and image created
from, etc.

### Save Image

Click **Save** to save the Workspace as a image named *myimage*, which
can be used later on. Now the image list is shown as:

<img src="../images/config-image.png" width="700" alt="image config">

Users can also **Share** their saved private images with others, to help
them avoid tedious installation and configuration stuff.

### TCP Port Mapping

Each Node can apply for a TCP port. The Node port will be mapped to the host port, and the TCP packets sent by the user to the host port will be transferred to this port. The service on the node needs to listen to the configured port.

The following picture shows the TCP port mapping webpage of **tee** Workspace:

<img src="../images/config-tcp.png" width="700" alt="image config">

Click **Apply** to add a TCP port mapping for a node：

<img src="../images/config-tcpapply.png" width="700" alt="image config">
