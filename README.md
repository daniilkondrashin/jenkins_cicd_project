Данный проект необходим для изучения на практическом примере. Jenkins. Был реализован непрерывный процесс интеграции Cicdcd. 
Исходный код микросервесов взял из этого репозитория: https://github.com/rinormaloku/k8s-mastery.git. 

Как был реализован сам процесс: 

Jenkins делает запрос каждую минуту на Githab. Если были изменения в репозитории, то он копирует его к себе и читает Jenkinsfiles. Далее начинается при необходимости Build, по завершению которого приложение собирается в Docker контейнер и отправляется на Dockerhub. После того как сборка и отправка всех микросервисов успешно завершена, запускается Pipeline, который вносит изменения в Kubernetes.
