-kubernetes also called as k8s
-because their are 8 letter between k and s in "ubernete"
-kubernetes take care of automatic deployement of applications on different
server
-distribution of the load across seerver 
-auto scaling of the deployed applications
monitoring and health check of the containers
-replacement of the failed continers



# supported container runtime 
docker , cri-o , containerd

# architecture of the kubernetes

## pod

pod anatomy --- pod is the smallest unit in the kubernetes world 
pod can contain multiple container with shared volume and shared ip address
{main scenario is have the single pod in the single container}

# kubernetes cluster

cluster consist of nodes{server can be virtual server and metal server}

inside the node we got pod and in pos we got conatiner

and all this done by kubernetes

## how nodes communicate each other

in kubernetes we have master node and it is the responsibnlity of master node
to distribute the load across the worker node ...
matser node only responsible for runing system port


## which services run in nodes

a node contain kubelet , kube -proxy , container runtime 
conatiner runtime actually run conatainer in the node

kube proxy is responsible for network communication

scheduler reposnible for distibuting load across node ..

cloud controller manager manages cloud service provider

etcd service has logs related operation related to entire k8s cluster 
 api server manages the worker node...


# kubectl cli(kube control)

manages to remotely k8s cluster
we are using rest api to connect k8s cluster
we connect to master node through kube ctl and then connect to the other worker
node through master node



