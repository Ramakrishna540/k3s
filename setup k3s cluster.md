# Setup K3s Cluster Documentation 

## K3s
<p>We wanted an installation of Kubernetes that was half the size in terms of memory footprint. Kubernetes is a 10 letter word stylized as k8s. So something half as big as Kubernetes would be a 5 letter word stylized as K3s. There is neither a long-form of K3s nor official pronunciation.</p>

<p>Let us move to installtion process</p>
<p>We can setup K3s cluster on any cloud but today we are doing on google cloud.Process is same in all clouds</p>

## Prerequisite
1.Google Cloud Account

>Task1
    
    Open your google cloud  and create your vitual machine with ubuntu 18.04 server

    After launching your vm click on ssh you can see there 

    After Launching to yourubuntu server follow below installation process


<p>The install.sh script provides a convenient way to download K3s and add a service to systemd or openrc.</p>

<p >To install k3s as a service, run:</p>


```
    curl -sfL https://get.k3s.io | sh ```

<p>A kubeconfig file is written to /etc/rancher/k3s/k3s.yaml and the service is automatically started or restarted. The install script will install K3s and additional utilities, such as kubectl, crictl, k3s-killall.sh, and k3s-uninstall.sh, for example:</p>

    sudo kubectl get nodes

<p>you can observe a master node is formed </p>

<p>
 <span style="color:blue">K3S_TOKEN</span>  is created at <span style="color:red">/var/lib/rancher/k3s/server/node-token</span> on your server.</p>
 <p><span style="color:blue"> To install on worker nodes, pass K3S_URL along with K3S_TOKEN or K3S_CLUSTER_SECRET environment variables, for example:</span></p>

 ### <p>For this create another vm and type follwing command</P>
 ```
    curl -sfL https://get.k3s.io | K3S_URL=https://myserver:6443 K3S_TOKEN=XXX sh -
```
### Here my server means ip of your master and you have to paste your token in place of xxx which is available in /var/lib/rancher/k3s/server/node-token 

<p>After that follow the command</p>
```
    sudo kubectl get nodes 
    
```
<p>Then you will see one master and one worker like below </p>

<span style="color:red">Refferences</span>

1.https://github.com/k3s-io/k3s/blob/master/README.md
2.https://www.youtube.com/watch?v=1hwGdey7iUU
