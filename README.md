# Тестовое задание в ЗИТ: Junior DevOps / Системный администратор (Linux)

## 1. Подготовка тестового окружения:

- На своём локальном ПК или виртуалке (например, Ubuntu 20.04+):

<img src="misc/img/1-1.png" width="400"/>

- Установите и настройте nginx

`sudo apt-get update && sudo apt-get -y install nginx`

Конфиг по умолчанию выдает стартовую страничку nginx на порт 80.

- Настройте systemd-сервис, чтобы nginx запускался при старте системы

`sudo systemctl enable nginx`

<img src="misc/img/1-2.png" width="600"/>

- Ожидаемый результат:

- Nginx работает

<img src="misc/img/1-3.png" width="600"/>

- systemctl status nginx показывает активное состояние

<img src="misc/img/1-4.png" width="600"/>

## 2. Напишите простой .gitlab-ci.yml файл

- Сценарий:
- Этап test должен запускать проверку наличия установленного nginx:
- - bash
- - Copy
- - Edit
- - which nginx && nginx -v

- Ожидаемый результат:
- Корректный файл .gitlab-ci.yml с минимальным пайплайном

gitlab-ci.yml:
```yml
stages:
  - test

test_job:
  stage: test
  script:
    - which nginx && nginx -v
```

- Комментарии внутри объясняют, что делает каждая стадия