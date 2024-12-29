# Домашнее задание к занятию 10 «Jenkins»

## Подготовка к выполнению

Пришлось переписывать роль для Ubuntu 22.04

Для выполнения задания был использован Jenkins 2.479.2

CentOS совсем стал плох. Вроде всё развернул, java обновил, но с питоном беда

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

Конечно-же, с первого раза ничего не получилось. С 15 попытки всё прошло успешно.

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

[Файл Declarative Pipeline](Jenkinsfile)

4. Создать Multibranch Pipeline.

Было немного непонятно, но полагаю что выполнение одновременно нескольких пайплайнов это и есть мультибранч пайплайн. у меня получилось вот так:

![alt text](multibranch.png)

5. Создать Scripted Pipeline.

Создание

![alt text](<scripted make.png>)

Выполнение пайплайна и консоль

![alt text](<scripted console.png>)

Результат

![alt text](<scripted result.png>)

Скрипт для Multibranch Pipeline пришлось переделать под свою репу в github и выполнить molecule test, поскольку для предложеной репы в файле нужен был ssh-key...

[Скрипт для Multibranch Pipeline](ScriptedJenkinsfile)

[Репозиторий, который был взят для пайплайна](https://github.com/gaidarvu/ansible-netology/tree/hw-ansible-05)

[Репозиторий, в котором лежит переделанная роль для jenkins и скрипты для пайплайнов](https://github.com/gaidarvu/jenkins-netology)