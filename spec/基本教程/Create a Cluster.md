# 教學 : Using Minikube to Create a Cluster

- https://kubernetes.io/docs/tutorials/kubernetes-basics/cluster-intro/
- 20180302
- v1.9

在 kube 中，元件有
- Master
- Node
- node processes

- Master 負責管理叢級
	- 協調所有在叢集中的行為，such as scheduling applications, maintaining applications' desired state, scaling applications, and rolling out new updates.
- Node
	- 一個 node 就有如一個 VM 或者說是實體電腦，在 kube cluster 中如一個工作機器般的運作
	- 每個 node 都有 **kubelet**，kubelet 負責管理 node 並與 kubernetes master 進行溝通
	- node 中也有工具處理 container 的操作，如 Docker or rkt
	- 一個 kube cluster 最小會有 3 個 nodes
- 部署時，會告訴 master 啟動 application containers. Master 會在 cluster 的 node 建立 containers. 而 node 跟 master 透過 Kubernetes API 進行溝通. 端點用戶也可以使用 API 直接操作.
- Kube cluster 可被部署在實體與虛擬機器上，在開發上，可使用 Minikube
- Minikube 是一個輕量化的，透過 VM 在本地端執行的機器，有如 kubernetes cluster
- Minikube CLI 提供基本的 cluster 操作 : start, stop, status, delete
- 在 google 的教學中，有 online 版本的操作，可提供練習 : [練習](https://kubernetes.io/docs/tutorials/kubernetes-basics/cluster-interactive/)
	
	
	