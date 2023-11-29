Step 1
kubectl create namespace monitoring# promethues-k8s-ingress

Add Helm repository
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://charts.helm.sh/stable
helm repo update

Install prometheus
helm install prometheus prometheus-community/kube-prometheus-stack

kubectl port-forward deployment/prometheus-grafana 3000

username: admin
password: prom-operator


helm install prometheus prometheus-community/prometheus

helm repo add grafana https://grafana.github.io/helm-charts
helm install grafana grafana/grafana

kubectl port-forward svc/grafana 3000:80


https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack
https://www.linkedin.com/pulse/use-case-deploying-grafana-prometheus-using-helm-charts-chandna/