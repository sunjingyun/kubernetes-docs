# How to create KUBECONFIG for remote access
#### 1. create serviceaccout
`kubectl apply -f kubernetes_add_service_account_kubeconfig_rbac_test.yaml`

#### 2. create config
`./kubernetes_add_service_account_kubeconfig.sh ${user-name} ${namespaces} ${hosts} ${https-cert-path}`

> such as:

`./kubernetes_add_service_account_kubeconfig.sh github test https://kubernetes.io /etc/nginx/cert/ca.pem`

### 3. access kubernetes clusters with config
`KUBECONFIG=${config_path} kubectl get pods`

### 4. support http2 in nginx if you are using helm
```
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection "upgrade";
```
