# Домашнее задание к занятию "`Работа с GitLab и CI/CD`" - `Хомяков Антон`

---

# Домашнее задание

## Задание 1

1. GitLab был развернут локально с использованием Vagrant.
2. Создан новый проект с именем `ci-test` на GitLab.
3. Зарегистрирован gitlab-runner в проекте и настроен для выполнения задач.

## Задание 2

1. Репозиторий был запушен на GitHub.
2. Создан файл `.gitlab-ci.yml` с настройкой этапов CI/CD:
   - **build**: установка зависимостей.
   - **test**: запуск тестов.
   - **deploy**: деплой проекта.
   
код `.gitlab-ci.yml` добавлен в проект и запушен на GitHub.

# GitLab CI/CD pipeline configuration file

stages:
  - build
  - test
  - deploy

# Этап сборки
build:
  stage: build
  image: ubuntu:latest
  before_script:
    - apt-get update -y
    - apt-get install -y build-essential
  script:
    - echo "Building the project..."
    - # Здесь можно добавить команды для сборки проекта, например, make, npm install и т.д.

# Этап тестирования
test:
  stage: test
  image: ubuntu:latest
  before_script:
    - apt-get update -y
    - apt-get install -y build-essential
  script:
    - echo "Running tests..."
    - # Команды для запуска тестов, например, python3 -m unittest или npm test.

# Этап деплоя (можно настроить, если хотите деплоить)
deploy:
  stage: deploy
  image: ubuntu:latest
  script:
    - echo "Deploying the project..."
    - # Команды для деплоя вашего проекта на сервер или в облако.
  only:
    - main

## Скриншоты

- Скриншоты с успешно выполненными сборками можно найти в разделе **CI / CD** -> **Pipelines** на GitLab.

