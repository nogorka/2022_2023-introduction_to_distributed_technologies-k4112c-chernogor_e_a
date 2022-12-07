    University: [ITMO University](https://itmo.ru/ru/)
    Faculty: [FICT](https://fict.itmo.ru)
    Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
    Year: 2022/2023
    Group: k4112c
    Author: Chernogor Ekaterina Alekseevna
    Lab: Lab2
    Date of create: 07.12.2022
    Date of finished: 


# Лабораторная работа №3 "Сертификаты и "секреты" в Minikube, безопасное хранение данных."

## Описание

В данной лабораторной работе вы познакомитесь с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

## Цель работы

Познакомиться с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.
---
## Ход работы
- [ ] Вам необходимо создать configMap с переменными: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.

- [ ] Вам необходимо создать replicaSet с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и используя ранее созданный configMap передать переменные REACT_APP_USERNAME, REACT_APP_COMPANY_NAME .

- [ ] Включить minikube addons enable ingress и сгенерировать TLS сертификат, импортировать сертификат в minikube.

- [ ] Создать ingress в minikube, где указан ранее импортированный сертификат, FQDN по которому вы будете заходить и имя сервиса который вы создали ранее.

### Подготовительная работа
```
$ minikube start
$ minikube ssh docker pull ifilyaninitmo/itdt-contained-frontend:master
```


### Основная работа 
1. Вам необходимо создать [configMap](config-map-manifest.yml) с переменными: `REACT_APP_USERNAME`, `REACT_APP_COMPANY_NAME`.

```
$ kubectl apply -f lab3/configmap-manifest.yml
> configmap/frontend-configmap created
```

2. Вам необходимо создать [replicaSet](replica-set-manifest.yml) с 2 репликами контейнера `ifilyaninitmo/itdt-contained-frontend:master` и используя ранее созданный configMap передать переменные `REACT_APP_USERNAME`, `REACT_APP_COMPANY_NAME` .
    * создаем манифест
    - применяем манифест `kubectl apply -f filename`
    - смотрим что работает  `kubectl get pods -w` `kubectl get rs -w`

```
$ kubectl apply -f lab3/replicaset-manifest.yml
> replicaset.apps/frontend-replicaset created
```
```
$ kubectl apply -f lab3/service-manifest.yml
> service/frontend-service created
```

3.

```
$ minikube addons enable ingress
```

```
sudo apt install libnss3-tools
curl -JLO "https://dl.filippo.io/mkcert/latest?for=linux/amd64"
chmod +x mkcert-v*-linux-amd64
sudo cp mkcert-v*-linux-amd64 /usr/local/bin/mkcert
```

```
mkcert -install

mkcert nogorka.com "*.nogorka.com" nogorka.test localhost 127.0.0.1 ::1
```
create ingress yaml manifest

```
$ kubectl apply -f lab3/ingress-manifest.yml

```


## Результаты и выводы


### Примечание

---
## Ссылки на материалы
1. [ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/)
2. [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/)
3. [Ingress DNS](https://minikube.sigs.k8s.io/docs/handbook/addons/ingress-dns/)
4. [How to use custom TLS certificate with ingress addon](https://minikube.sigs.k8s.io/docs/tutorials/custom_cert_ingress/)
5. [mkcert](https://github.com/FiloSottile/mkcert)
6. [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
7. []()