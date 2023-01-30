****<!-- 
Minikube is a utility you can use to run Kubernetes (k8s) on your local machine. It creates a single node cluster contained in a virtual machine (VM). This cluster lets you demo Kubernetes operations without requiring the time and resource-consuming installation of full-blown K8s.

 -->

if you dont give root access to docker remember use sudo before every command
- sudo systemctl docker start
- sudo minikube start --force 
- sudo minikube status
- 

    there is another docker container running inside the k8s cluster

- sudo kubectl get pods
 to check all the availbale pods in minikube

 <!-- 
 
 
  -->



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

- now kubectl get pods only show pods availbale inside default namespaces are there more namespaces yes there are more namespacees to check those you need 
    - sudo kubectl get namespaces
        - after that you get default , kube-node-lease , kube-public , kube-system namespaces and inside default namespace you get pods that we are going to create
- sudo kubectl get pods --namespace=kube-system

    - to access particular namespace

- sudo kubectl run nginx --image=nginx 
 - we are going to create a pod of nginx now here we are going to get nginx image through docker by default imageof nginx and it will be are our first pod

- instead of using help of kubectl command to run docker command you can just ssh into minkube and use docker command as usual as you do

- sudo kubectl describe pod || pod name||
- docker exec -it --id of conatiner-- sh
        - use to connect the particular continer
- now to get the ip of container that runing nginx can get by two ways one is ssh into minikube use docker exec command to get into nginx container then use hostname -i to get the ip but 

- how we gonna do this with help of kubectl it is so simple 
    - sudo kubectl get pods -o wide
    - you gonna get ip of all pods

- now we all know if hit nginx conatiner ip we gonna get default nginx page so lets hit that ip but from our terminal not going to  ssh into minikube then into conatiner nahhhhh

- to do this 
    - sudo kubectl delete pod nginx
    - alias k="sudo kubectl"
    - k create deployement nginx --image=nginx
    - k describe deployment nginx
            - after runing describe command we get selector which use to connect with port
    - k describe pod --name of the pod---
        - you get name of pod by k get pods
    - k scale deployment nginx --replicas=5
        - it will create 5 replica of nginx basically scale up the nginx 
    - k scale deployment nginx --replicas=3
        - it will scale down to 3
