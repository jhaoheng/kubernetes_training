# install minikube
> 請先安裝好 kubectl

1. 安裝 [virtual box](https://www.virtualbox.org/wiki/Downloads)
	- 此次安裝的版本為 5.2.8
	- mac 安裝失敗問題 : http://blog.csdn.net/u013247765/article/details/78176079
		- mac 安全性與隱私問題
2. osx 安裝 minikube : `brew cask install minikube`
3. 啟動 minikube : `minikube start`
	- 若遇到失敗 : `minikube delete`
	- 開啟控制台 : `minikube dashboard`
4. use
	- [操作方法](https://kubernetes.io/docs/tutorials/stateless-application/hello-minikube/)
	- [Github](https://github.com/kubernetes/minikube)