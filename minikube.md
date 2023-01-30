<!-- 
Minikube is a utility you can use to run Kubernetes (k8s) on your local machine. It creates a single node cluster contained in a virtual machine (VM). This cluster lets you demo Kubernetes operations without requiring the time and resource-consuming installation of full-blown K8s.

 -->

if you dont give root access to docker remember use sudo before every command
->sudo systemctl docker start
->sudo minikube start --force 
->sudo minikube status
->
{
    there is another docker container running inside the k8s cluster
}
<!-- 
    command for that is
 -->
 {
    each node in k8s is sever {either physical or virtual}
    we can connect with ssh
 }
->minikube ip {for ip of node runing in k8s }
->ssh docker@<ip by minikube>
<!-- 
    by default passowrd is tcuser and 
    username is docker
 -->