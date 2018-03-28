# kubernates 基本結構

- kubectl 					: 客戶端命令行工具，將接受的命令格式化後發送給 kube-apiserver，作為整個系統的操作入口。
- kube-apiserver 			: 作為整個系統的控制入口，以 REST API 服務提供接口。
- kube-controller-manager 	: 用來執行整個系統中的後台任務，包括節點狀態狀況、Pod 個數、Pods 和 Service 的關聯等。
- kube-scheduler 			: 負責節點資源管理，接受來自 kube-apiserver 創建 Pods 任務，並分配到某個節點。
- etcd 						: 負責節點間的服務發現和配置共享。
- kube-proxy 				: 運行在每個計算節點上，負責 Pod 網絡代理。定時從 etcd 獲取到 service 信息來做相應的策略。
- kubelet					: 運行在每個計算節點上，作為 agent，接受分配該節點的 Pods 任務及管理容器，周期性獲取容器狀態，反饋給 kube-apiserver。
- DNS 						: 一個可選的DNS服務，用於為每個 Service 對象創建 DNS 記錄，這樣所有的 Pod 就可以通過 DNS 訪問服務了。

> 原文網址：https://read01.com/BJ8Rze.html