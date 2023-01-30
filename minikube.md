****<!-- 
Minikube is a utility you can use to run Kubernetes (k8s) on your local machine. It creates a single node cluster contained in a virtual machine (VM). This cluster lets you demo Kubernetes operations without requiring the time and resource-consuming installation of full-blown K8s.

 -->

if you dont give root access to docker remember use sudo before every command
- sudo systemctl docker start
- sudo minikube start --force 
- sudo minikube status
- 

    there is another docker container running inside the k8s cluster





    - each node in k8s is sever {either 
    - physical or virtual}
    - we can connect with ssh
- minikube ip {for ip of node runing in k8s 
- ssh docker@<ip by minikube>

    - by default passowrd is tcuser and 
    - username is docker

 - or you can use ...
 -  sudo minikube ssh**

 if wnat to see docker conatiner runing 
 - use sudo docker ps


 now after ssh into minikube 

 - we do kubeclt and we see command not found becuase inside k8s cluster and inside that docker conatiner is runing so no kubectl is installed inside that conatiner

 - kubectl is only avialble out k8s

 - kubectl cluster-info {give you cluster info}

 - sudo kubectl get nodes {give you node runing inside minikube by default only one node run on the minikube}**