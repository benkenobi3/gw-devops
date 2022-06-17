#### Подготовка миникуба
    minikube start --kubernetes-version 1.21.2
    kubectl apply --validate=false -f https://github.com/jetstack/cert-manager/releases/download/v0.15.1/cert-manager.crds.yaml


#### Билд
    heml install build ./Helm/Build
    heml install build ./Helm/Build -f ./Helm/Build/front_values.yaml

#### Запуск
    helm install app ./Heml/Apps

