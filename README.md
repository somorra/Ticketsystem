# Ticketsystem

K

curl -sfL https://get.k3s.io/ | sh -s - server \
  --server https://10.69.69.2:6443/ \
  --token <token> \
  --node-taint node-role.kubernetes.io/control-plane=true:NoSchedule

curl -sfL https://get.k3s.io/ | INSTALL_K3S_EXEC="server --server https://kronos01:6443/" K3S_TOKEN=<token> sh -

  --enable-worker=true

curl -sfL https://get.k3s.io/ | INSTALL_K3S_EXEC="server --server https://kronos01:6443/ --enable-worker=true" K3S_TOKEN=<token> sh -

curl -sfL https://get.k3s.io/ | K3S_URL=https://kronos01:6443/ K3S_TOKEN=<token> sh -

curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
helm version

helm repo add longhorn https://charts.longhorn.io/
helm repo update
helm upgrade --install longhorn longhorn/longhorn --namespace longhorn-system --create-namespace


helm repo add zammad https://zammad.github.io/zammad-helm
helm repo update
helm upgrade --install zammad zammad/zammad --namespace zammad --create-namespace

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm upgrade --install ingress-nginx ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace


helm upgrade --install zammad zammad/zammad -f values.yaml --namespace zammad
