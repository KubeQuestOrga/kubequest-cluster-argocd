# KubeQuest - Argo CD - Cluster K3s

## ⚙ Setup Environment
1. Connect to the NODE MASTER in Cluster K3S.
2. Install HELM : https://helm.sh/docs/intro/install/
3. Use repo argo-cd HELM : https://artifacthub.io/packages/helm/argo/argo-cd
4. Récupérer les fichiers manifest dans : k8s/, puis les déposer sur le serveur.
5. Run command :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo helm repo add argo https://argoproj.github.io/argo-helm
sudo helm repo update
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm install my-argo-cd argo/argo-cd --version 8.1.1 --namespace argo-cd --create-namespace
```

<br /><br /><br /><br />


## 🚀 Update chart CertManager HELM for values.yaml
1. Connect to the NODE MASTER in Cluster K3S.
2. Récupérer les fichiers manifest dans : k8s/, puis les déposer sur le serveur.
3. Run command :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm upgrade my-argo-cd argo/argo-cd --namespace argo-cd --values values.yaml
```
