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

### Custom WEB access

Docklet provides each vcluster a custom URL that could be used to access
internal WEB service. Users can define which container this URL is
proxied to. 

<img src="../images/config-proxy.png" alt="proxy service">

The above is an example showing that the user *root* has a Workspace
named *note*, which has a public URL of 

`http://iwork.internetware.org/_web/root/note`

The user configures this URL to be proxied to one of his container
`172.16.0.45:80`.

If an nginx server is running at `172.16.0.45`, then the following
directives could be put in `/etc/nginx/site-enabled/default`

```
location /_web/root/test/  {
    proxy_pass http://localhost/ ;
}
```

Restart nginx, 

```
$ service nginx restart
```

then the above URL could be accessed from outside.
