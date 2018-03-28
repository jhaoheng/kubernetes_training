# 透過 docker 使用 kubernetes

## SYNOPSIS
- 進行部署測試
	- 在 mac 上，在本地端使用 kubernetes cluster & client 
	- 透過本地部署測試來降低雲端部署的錯誤
- kubernetes cluster
	- 實踐日期 20180301, 未來或許會有更好的方法進行測試
	- docker for mac 這個應用程式本身就包含 kubernetes cluster 的建立，故不採用 minikube
	- 關於 minikube，須先安裝 vm 服務 (virtualbox) 才能使用
- kubenetes client 則透過[官網安裝](https://kubernetes.io/docs/imported/release/notes/)即可

## Environment
- osx
- docker community edition version 18.03.0-ce, channel:edge. 此版本在 20180301 支援 kubernetes 的整合.
- kubectl version
	- Client Version: version.Info{Major:"1", Minor:"9", GitVersion:"v1.9.1", GitCommit:"3a1c9449a956b6026f075fa3134ff92f7d55f812", GitTreeState:"clean", BuildDate:"2018-01-04T11:52:23Z", GoVersion:"go1.9.2", Compiler:"gc", Platform:"darwin/amd64"}
	- Server Version: version.Info{Major:"1", Minor:"9", GitVersion:"v1.9.2", GitCommit:"5fa2db2bd46ac79e5e00a4e6ed24191080aa463b", GitTreeState:"clean", BuildDate:"2018-01-18T09:42:01Z", GoVersion:"go1.9.2", Compiler:"gc", Platform:"linux/amd64"}

## install

- 安裝 docker edge 
	- 說明 : [kubernetes in docker](https://docs.docker.com/docker-for-mac/#kubernetes)
	- [下載](https://docs.docker.com/docker-for-mac/install/#download-docker-for-mac)
	- 注意，如果原本使用 stable 版本，既有的 image 全部都會被清空
- 安裝 kubernetes client [官網安裝](https://kubernetes.io/docs/imported/release/notes/)
	1. 進入安裝頁面
	2. 選擇 client binaries
	3. 確定自己電腦的 linux 安裝即可 : osx amd64 
		- `uname -a` : 看是否是 x86_64
		- `shasum -a 256 {the file} | grep {hash}` : 在 osx 驗證 hash
	4. 放入 bash_profile, `source ~/.bash_profile` 即可

## 設定 kubenetes cluster

1. 安裝好 docker for mac edge
2. 進入 Perference
3. 選擇 Kubernetes
4. 勾選 
	- [x] : Enable Kubennetes
	- [x] : Show system containers(advanced)
5. apply 後，如下圖

![img1](https://raw.githubusercontent.com/jhaoheng/assets/master/blog/docker/docker-kubectl-1.png)

## 設定 kubenetes client

1. 安裝好 client 後，執行 `kubectl version`，會出現 server 並沒有指定的錯誤
2. 執行 `kubectl config get-contexts`
3. 設定 `kubectl config use-context docker-for-desktop`
4. 再執行一次 `kubectl version`

## 檢查 docker

1. 此時透過 docker ps，會看到以下資訊，這些都是掛載的 kube cluster
![img2](https://raw.githubusercontent.com/jhaoheng/assets/master/blog/docker/docker-kubectl-2.png)
2. 回到 docker kube perference 下，將以下取消勾選
	- [ ] : Show system containers(advanced)
3. 在執行一次，就會發現相關服務被隱藏起來