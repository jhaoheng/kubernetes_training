
# Synopsis
- 透過本地端，練習 kubenetes client 
- 使用 minikube&virtualbox 當作 kube cluster
- minikube 本身提供像 gcloud 一樣 GUI 介面，方便具有既視感
	- docker 本身提供的 kubernetes cluster 目前沒有 GUI 介面

# use

1. kubectl 取得授權 : `kubectl config use-context minikube`
2. `kubectl create -f {config.yml}`
3. `kubectl get servies`
	- 會看到 external-ip 一直都會是 pending 的狀態
	- 使用 `minikube service {service-name}`
4. `kubectl delete -f {config.yml}`