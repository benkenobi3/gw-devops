#### Подготовка кубернетес
    minikube start --kubernetes-version 1.21.12

    kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.8.0/cert-manager.yaml

#### Подготовка ингресс контроллера
    kubectl create namespace ingress-nginx
    helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    helm repo update
    helm install ingress-nginx ingress-nginx/ingress-nginx --namespace ingress-nginx

#### Билд
    heml install build ./Helm/Build
    heml install build ./Helm/Build -f ./Helm/Build/front_values.yaml

#### Запуск
    helm install app ./Heml/Apps
