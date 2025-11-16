```bash
kind create cluster --name my-cluster --config configNoNetworkPlugin.yaml
```
```bash
kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml
```
```bash
kubectl exec -it "Pod Name" -- sh
```
```bash
curl "Pod Name":80
```
```bash
nc -zv mysql 3306
```
```bash
kubectl create -f policy-definition.yaml
```
```bash
openssl genrsa -out tamim.key 2048
```
```bash
openssl req -new -key tamim.key -out tamim.csr -subj "/CN=tamim"
```
```bash
cat tamim.csr | base64 | tr -d "\n"
```
```bash
kubectl apply -f csr.yaml
```
```bash
kubectl get csr
```
```bash
kubectl certificate approve tamim
```
```bash
kubectl get csr tamim -o yaml > tamim-issuedcert.yaml
```
```bash
echo "The certificate from the yaml file" | base64 -d
```
```bash
kubectl create -f role.yaml
kubectl create -f rolebinding.yaml
```
```bash
kubectl get rolebinding
kubectl describe rolebinding read-pods "[Role Binding Name]"
```
```bash
kubectl auth can-i get pod --as tamim "[User Name]"
```
"Count All Roles"
```bash
kubectl get roles -A --no-headers | wc -l
```
```bash
kubectl config set-credentials tamim --client-key=tamim.key --client-certificate=tamim.crt --embed-certs=true
```
```bash
kubectl config set-context tamim --cluster=kind-kind --user=tamim
```
```bash
kubectl config get-contexts
```
```bash
kubectl config use-context tamim
```