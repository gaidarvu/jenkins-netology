# Домашнее задание к занятию 10 «Jenkins»

## Подготовка к выполнению

Пришлось переписывать роль для Ubuntu 20.04

CentOS совсем стал плох. Вроде всё развернул, java обновил, но с питоном там беда

## Основная часть

1. Добавление Freestyle Job, который будет запускать `molecule test` из репозитория с ролью Vector.

Добавление репозитория (credentials для гита добавил но не заскриншотил)

![alt text](<freestyle add git.png>)

Выбор нужной ветки

![alt text](<freestyle add git 2.png>)

Какие команды будут выполняться

![alt text](<freestyle shell.png>)

Тест прошел успешно

![alt text](<freestyle console.png>)

Конечно-же, с первого раза ничего не получилось. С 10 попытки всё прошло успешно.

![alt text](<freestyle result.png>)

2. Добавление Declarative Pipeline Job, который будет запускать `molecule test` из репозитория с ролью Vector.

Добавление репозитория 

![alt text](<pipeline add git.png>)

Путь до скрипта

![alt text](<pipeline add git 2.png>)

Выполнение в процессе

![alt text](<pipeline console.png>)

Результаты

![alt text](<pipeline result.png>)

![alt text](<pipeline result2.png>)

3. Declarative Pipeline в репозитории в файле `Jenkinsfile`.

[Declarative Pipeline](Jenkinsfile)

4. Создать Multibranch Pipeline на запуск `Jenkinsfile` из репозитория.
5. Создать Scripted Pipeline, наполнить его скриптом из [pipeline](./pipeline).
6. Внести необходимые изменения, чтобы Pipeline запускал `ansible-playbook` без флагов `--check --diff`, если не установлен параметр при запуске джобы (prod_run = True). По умолчанию параметр имеет значение False и запускает прогон с флагами `--check --diff`.
7. Проверить работоспособность, исправить ошибки, исправленный Pipeline вложить в репозиторий в файл `ScriptedJenkinsfile`.
8. Отправить ссылку на репозиторий с ролью и Declarative Pipeline и Scripted Pipeline.
9. Сопроводите процесс настройки скриншотами для каждого пункта задания!!

## Необязательная часть

1. Создать скрипт на groovy, который будет собирать все Job, завершившиеся хотя бы раз неуспешно. Добавить скрипт в репозиторий с решением и названием `AllJobFailure.groovy`.
2. Создать Scripted Pipeline так, чтобы он мог сначала запустить через Yandex Cloud CLI необходимое количество инстансов, прописать их в инвентори плейбука и после этого запускать плейбук. Мы должны при нажатии кнопки получить готовую к использованию систему.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
