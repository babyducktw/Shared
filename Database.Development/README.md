# Database for dev
此專案用於定義 Babyduck 宇宙在 local 開發時的資料庫基礎建設

關於 SQL SERVER 跑在 K8S 的最佳實踐可以參考微軟的這篇
https://learn.microsoft.com/zh-tw/sql/linux/sql-server-linux-kubernetes-best-practices-statefulsets

### 有用的指令
Windows
```shell
set DEV_CONTEXT "docker-desktop"
```
Linux
```shell
DEV_CONTEXT="docker-desktop"
```
> 將 "docker-desktop" 替換成你的 kube context 名稱
#### 應用變更
```shell
kubectx $DEV_CONTEXT && helm upgrade my-db ./
```
#### 第一次執行
```shell
kubectx $DEV_CONTEXT && helm install my-db ./
```
```shell
kubectl create namespace babyduck-db
```
#### 移除
```shell
kubectx $DEV_CONTEXT && helm uninstall my-db
```
```shell
kubectl delete namespace babyduck-db
```
