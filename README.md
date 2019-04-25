# Kube-scripts for setting up Roles and RolesBinding 

Nice wb refernces :

https://brancz.com/2017/10/16/kubernetes-auth-x509-client-certificates/

https://jenciso.github.io/personal/manage-tls-certificates-for-kubernetes-users

https://medium.com/@amimahloof/how-to-setup-helm-and-tiller-with-rbac-and-namespaces-34bf27f7d3c3




# To Modify Kube Config file

kubectl config set-cluster "${CLUSTER_NAME}" --kubeconfig=kubenew/config-new --server="${ENDPOINT}" --certificate-authority=kubenew/ca.crt --embed-certs=true

kubectl config set-credentials tiller-dev-k8s --kubeconfig=kubenew/config-new --token="${TOKEN}"

kubectl config set-context tiller-dev-k8s --kubeconfig=kubenew/config-new --cluster="${CLUSTER_NAME}" --user=tiller-dev-k8s --namespace=prod

kubectl config use-context tiller-dev-k8s --kubeconfig=kubenew/config-new

# To Check 

KUBECONFIG=kubenew/config-new kubectl get pods

kubectl run nginx --image=nginx:latest --replicas=3 --port=80 -n prod

KUBECONFIG=kubenew/config-new kubectl get pods
