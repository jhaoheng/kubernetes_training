https://s3.amazon      aws.com/quickstart-reference/heptio/latest/doc/heptio-kubernetes-on-the-aws-cloud.pdf


1. 使用 aws : CloudFormation
- 基本操作

2. 取得本地端操作授權 (亦可登入 master 直接進行 kubernetes 的操作)
> 此行為雷同 `gcloud container clusters get-credentials {CLUSTER_NAME}` 

- `SSH_KEY=... ; scp -i $SSH_KEY -o ProxyCommand="ssh -i \"${SSH_KEY}\" ubuntu@{BastionHostPublicIP} nc %h %p" ubuntu@{MasterPrivateIP}:~/kubeconfig ./kubeconfig`

- 會儲存 kubeconfig
- 為了之後方便操作，在本地建立環境參數 : `export KUBECONFIG=$(pwd)/kubeconfig`

3. deploy to aws use config
- kubectl create -f config.yml
- kubectl get services
- kubectl delete -f config.yml