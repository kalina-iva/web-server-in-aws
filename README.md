# Веб-сервер в инфраструктуре AWS

---

## Для чего нужен этот репозиторий

Создание новой VPC с публичным сабнетом и инстансом в нем.
Запуск с помощью ansible веб-сервера nginx в докере.

---

## Что нужно сделать, чтобы запустить веб-сервер

### Создание vpc

Выполнить команды из директории vpc

```terraform init```

```terraform apply```

***note**: В main.tf в провайдере нужно указать ключи доступа или профиль*

На выходе получим `instance_ip`

### Запуск веб-сервера

В `inventory.yml` подставить `instance_ip`, полученный на предыдущем шаге и выполнить команду из директории ansible

```ansible-playbook playbook.yml -i inventory.yml```

Проверить, что веб-сервер запущен по адресу http://`instance_ip`