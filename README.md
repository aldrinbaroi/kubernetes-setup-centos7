# kubernetes-setup
Script to setup Kubernetes cluster on ***CentOS 7 & Ubuntu***

**kubernetes-setup usage:**
```      
kubernetes-setup -b [-s] | -j | (-s|-r) SETUP_OPTIONS | -h
         
-b     Get Kubenetes dashboard URL & login token only
       -s Setup dashboard & get dashboard URL & login token
-j     Get worker node's cluster join command
-s|-r  Setup/reinstall kubernetes node (master|worker)
-h     Show this usage text
         
SETUP_OPTIONS: -t node-type [-n node-name] [-i node-iface -a node-ip] [-c] [-d log-dir]
         
-t node-type    Kubernetes node type [master|worker]
-n node-name    Kubernetes node's host name
-i node-iface   Kubernetes node's network interface name
-a node-ip      IP address & netmask  Ex:  172.16.0.2/255.255.0.0
-c              Setup dashboard. Only applies to master node. By default dashboard is not setup
-d log-dir      Overrides default log directory 
```
**kubernetes-setup config file: kubernetes-setup.conf**
```
Change the following to match your setup:

KMASTER_IP_ADDRESS  Master node's IP address
KMASTER_NODE        Master node's IP address, hostname, short hostname
KWORKER_NODES       List of worker nodes' IP address, hostname, short hostname
KADMIN_USER         Admin user's login ID
KADMIN_PASSWORD     Admin user's login password
```
**Notes:** 
Admin user will be created if the user doesn't exists.

**Example:**

Setup master node
```
kubernetes-setup -s -t master -n kmaster
```
Setup worker node
```
kubernetes-setup -s -t worker -n kworker1
```
**Note:** Please make sure node name matches to what you have defined in the config file.
