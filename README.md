# How to create KUBECONFIG for remote access
#### 1. create serviceaccout
`kubectl apply -f kubernetes_add_service_account_kubeconfig_rbac_test.yaml`

#### 2. create config
`./kubernetes_add_service_account_kubeconfig.sh ${user-name} ${namespaces} ${hosts} ${https-cert-path}
`./kubernetes_add_service_account_kubeconfig.sh github test https://kubernetes.io /etc/nginx/cert/ca.pem`
