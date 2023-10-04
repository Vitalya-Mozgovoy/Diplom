## Monitoring-Kubernetes-with-Prometheus-Grafana

install Helm

$curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3

$chmod 700 get_helm.sh

$./get_helm.sh


Steps to Install:
--------------------------------

$kubectl create namespace monitoring


$helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

$helm install stable prometheus-community/kube-prometheus-stack --namespace=monitoring

### Чтобы подключится к серверу извне перенастроим сервисы prometheus и grafana. NodePort

$kubectl edit svc stable-kube-prometheus-sta-prometheus -n monitoring

$kubectl edit svc stable-grafana -n monitoring


### Steps to login/pass Grafana:
--------------------------

UserName: admin
Password: prom-operator