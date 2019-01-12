# kube-scripts

# TO Modify Config file

kubectl config set-cluster "${CLUSTER_NAME}" --kubeconfig=kubenew/config-new --server="${ENDPOINT}" --certificate-authority=kubenew/ca.crt --embed-certs=true

kubectl config set-credentials tiller-dev-k8s --kubeconfig=kubenew/config-new --token="${TOKEN}"

kubectl config set-context tiller-dev-k8s --kubeconfig=kubenew/config-new --cluster="${CLUSTER_NAME}" --user=tiller-dev-k8s --namespace=prod

kubectl config use-context tiller-dev-k8s --kubeconfig=kubenew/config-new

# To Check 

KUBECONFIG=kubenew/config-new kubectl get pods
