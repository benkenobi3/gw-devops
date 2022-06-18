#### Подготовка кубернетес
    minikube start --kubernetes-version 1.21.12


    kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.8.0/cert-manager.yaml


#### Подготовка ингресс контроллера
    kubectl create namespace ingress-nginx
    helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    helm repo update
    helm install ingress-nginx ingress-nginx/ingress-nginx --namespace ingress-nginx

#### Запуск дашборда и получения токена
    kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.0/aio/deploy/recommended.yaml
    kubectl apply -f dashboard.yaml
    kubectl get secret --namespace=kubernetes-dashboard
    kubectl get secret admin-user-token-XXXX --namespace=kubernetes-dashboard -o yaml
    kubectl proxy

Переход на
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

#### Билд
    heml install build ./Helm/Build
    heml install build ./Helm/Build -f ./Helm/Build/front_values.yaml

#### Запуск
    helm install app ./Heml/Apps
