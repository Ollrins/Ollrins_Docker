# Домашнее задание к занятию 5. «Практическое применение Docker»

## Задание 1: FastAPI приложение с MySQL


### 1. Создание Dockerfile.python (single stage)
<p align="center">
  <img src="screenshots2/dockerfile-single.png" alt="Dockerfile.python single stage" width="800"/>
  <br>
  <em>Рисунок 1 - Создание Dockerfile.python с базовым образом python:3.12-slim и конструкцией COPY .</em>
</p>

### 2. Создание .dockerignore
<p align="center">
  <img src="screenshots2/dockerignore.png" alt=".dockerignore файл" width="700"/>
  <br>
  <em>Рисунок 2 - Файл .dockerignore для исключения ненужных файлов</em>
</p>

### 3. Сборка и тестирование single stage образа
<p align="center">
  <img src="screenshots2/build-single.png" alt="Сборка single stage образа" width="900"/>
  <br>
  <em>Рисунок 3 - Сборка образа командой docker build -f Dockerfile.python -t test-app . </em>
</p>

### 4. Multistage сборка
<p align="center">
  <img src="screenshots2/dockerfile-multi.png" alt="Dockerfile.python multistage" width="800"/>
  <br>
  <em>Рисунок 4 - Изменение Dockerfile.python на multistage сборку</em>
</p>

<p align="center">
  <img src="screenshots2/build-multi.png" alt="Сборка multistage образа" width="900"/>
  <br>
  <em>Рисунок 5 - Сборка multistage образа test-app-multi</em>
</p>

### 5. ✨ Запуск с venv (без Docker)
<p align="center">
  <img src="screenshots2/mysql-container.png" alt="Запуск MySQL контейнера" width="900"/>
  <br>
  <em>Рисунок 6 - Запуск MySQL в контейнере для локальной разработки. Создание и активация виртуального окружения, установка зависимостей. </em>
</p>

<p align="center">
  <img src="screenshots2/venv-run.png" alt="Запуск приложения через venv" width="900"/>
  <br>
  <em>Рисунок 7 - Запуск приложения через uvicorn на порту 5001 (подключение к БД успешно)</em>
</p>

<p align="center">
  <img src="screenshots2/venv-curl.png" alt="Проверка через curl" width="800"/>
  <br>
  <em>Рисунок 8 - Проверка работы приложения через curl (получено предупреждение)</em>
</p>

### 6. ✨ Добавление ENV переменной DB_TABLE
<p align="center">
  <img src="screenshots2/main-py-config.png" alt="Изменение конфигурации в main.py" width="850"/>
  <br>
  <em>Рисунок 9 - Добавление переменной db_table в секцию конфигурации</em>
</p>

<p align="center">
  <img src="screenshots2/custom-table-start.png" alt="Запуск с кастомной таблицей" width="900"/>
  <br>
  <em>Рисунок 10 - Запуск приложения с DB_TABLE='my_custom_table' (таблица создана)</em>
</p>

<p align="center">
  <img src="screenshots2/custom-table-curl.png" alt="Проверка с кастомной таблицей" width="800"/>
  <br>
  <em>Рисунок 11 - Проверка работы с кастомной таблицей через curl</em>
</p>

## Задание 2
<p align="center">
  <img src="2_v.png" alt="Отчет сканирования" width="800"/>
  <br>
  <em>Рисунок 12 - Отчет сканирования</em>
</p>

## Задание 3
<p align="center">
  <img src="3_v.png" alt="Скриншот sql-запроса" width="800"/>
  <br>
  <em>Рисунок 13 - Скриншот sql-запроса</em>
</p>

## Задание 4
<p align="center">
  <img src="screenshots2/4v.png" alt="Скриншот sql-запроса" width="800"/>
  <br>
  <em>Рисунок 14 - Скриншот sql-запроса</em>  <br>
  <em>Ссылка на fork https://github.com/Ollrins/shvirtd-example-python.git</em>
</p>
## Необязательная часть
<p align="center">
  <img src="screenshots2/4v5.png" alt="Remote ssh context" width="800"/>
  <br>
  <em>Рисунок 15 - Remote ssh context</em>
</p>

## Задание 5
<p align="center">
  <img src="screenshots2/5v2.png" alt="Скрипт, cron-task и скриншот с несколькими резервными копиями в "/opt/backup" width="800"/>
  <br>
  <em>Рисунок 16 - Скрипт, cron-task и скриншот с несколькими резервными копиями в "/opt/backup" (из образа schnitzler/mysqldump не получилось) </em>
</p>

## Задание 6
<p align="center">
  <img src="screenshots2/6_dive.png" alt="dive" width="800"/>
  <br>
  <em>Рисунок 17 -Скриншот dive, вроде что-то пошло не так)</em>
</p>
<p align="center">
  <img src="screenshots2/6_terraform.png" alt="Скриншот terraform" width="800"/>
  <br>
  <em>Рисунок 18 - Скриншот terraform</em>
</p>

## Задание 6.1
<p align="center">
  <img src="screenshots2/6v1.png" alt="docker cp" width="800"/>
  <br>
  <em>Рисунок 19 - Скриншот docker cp </em>
</p>

## Задание 6.2
<p align="center">
  <img src="screenshots2/6_2v1.png" alt="docker build и Dockerfile" width="800"/>
  <br>
  <em>Рисунок 20 - Скриншот docker build и Dockerfile </em>
</p>

## Задание 7
<p align="center">
  <img src="screenshots2/7vC.png" alt="runC" width="800"/>
  <br>
  <img src="screenshots2/7v2.png" alt="runC" width="800"/>
    <br>
  <em>Рисунок 21 - Скриншот runC, дальше не получилось </em>
</p>












