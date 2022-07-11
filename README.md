# minicrud
nginx-deploy скачан отсюда: https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.2.0/deploy/static/provider/cloud/deploy.yaml (https://kubernetes.github.io/ingress-nginx/deploy/#quick-start)

#port-forwadding
# взято отсюда: https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/
kubectl port-forward deployment/minicrud 8000:8000

#ingress
надо в /etc/hosts добавить:
127.0.0.1       arch.homework

ingress настроен по требованиям второго дз - при переходе на http://arch.homework/otusapp/vitalii/ отображается главная страница.
добавление после .../vitalii/ какого-либо имени никакого эффекта не даёт - повторюсь, так настроен ingress (../vitalii/{etc_path/.../)

#kube secrets
kubectl create secret generic postgres-secret --from-literal=POSTGRES_DB=minicrud_db --from-literal=POSTGRES_USER=minicrud --from-literal=POSTGRES_PASSWORD=minicrud
