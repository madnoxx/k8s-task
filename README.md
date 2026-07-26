Веб-приложение, состоящее из фронтенда, бэкенда и PostgreSQL, развернутое в кластере Kubernetes через kubeadm.

## Структура репозитория

* backend/ - исходный код backend на Python Flask и Dockerfile
* frontend/ - статические файлы фронтенда и Dockerfile
* manifests/ - основные манифесты Kubernetes
    * backend/ - Deployment, Service, ConfigMap, PDB
    * frontend/ - Deployment, Service, ConfigMap, PDB
    * ingress/ - Ingress-ресурс
    * postgres/ - Cluster
    * security/ - NetworkPolicy, RBAC
    * storage/ - StorageClass: NFS и CSI-драйвер

## Реализовано

- Deployment и Service для frontend и backend
- Отказоустойчивый PostgreSQL через CloudNativePG в 3 репликах
- Хранилище через NFS и CSI-драйвер
- ConfigMap и Secret для конфигурации
- Ingress с HTTPS и редиректом с HTTP
- NetworkPolicy
- ServiceAccount и RBAC для backend
- PodDisruptionBudget для backend и frontend
- HTTPS на Ingress
- HashiCorp Vault для управления секретами

Реальные пароли не хранятся в репозитории. Пример команды создания - в manifests/postgres/secret_example.yaml.
