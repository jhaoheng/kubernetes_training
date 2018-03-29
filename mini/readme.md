# Synopsis

- 透過本地端，練習 kubenetes client 
- 使用 minikube&virtualbox 當作 kube cluster
- minikube 本身提供像 gcloud 一樣 GUI 介面，方便具有既視感
	- docker 本身提供的 kubernetes cluster 目前沒有 GUI 介面
- Minikube 是一個輕量化的，透過 VM 在本地端執行的機器，有如 kubernetes cluster
- Minikube CLI 提供基本的 cluster 操作 : start, stop, status, delete

# 前期操作
1. 確定 cluster 建立, ex : `minikube start`
2. 確定 image 推上 registry


# deploy
## use config to deploy

1. kubectl 取得授權 : `kubectl config use-context minikube`
2. `kubectl create -f {config.yml}`
3. `kubectl get servies`
	- 會看到 external-ip 一直都會是 pending 的狀態
	- 使用 `minikube service {service-name}`
4. `kubectl delete -f {config.yml}`