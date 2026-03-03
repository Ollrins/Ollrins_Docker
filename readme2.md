# Домашнее задание к занятию 5. «Практическое применение Docker»

## Задание 1: FastAPI приложение с MySQL

### 1. Создание fork репозитория
<p align="center">
  <img src="screenshots2/fork-repo.png" alt="Fork репозитория shvirtd-example-python" width="900"/>
  <br>
  <em>Рисунок 1 - Создание fork репозитория shvirtd-example-python в своем GitHub аккаунте</em>
</p>

### 2. Создание Dockerfile.python (single stage)
<p align="center">
  <img src="screenshots2/dockerfile-single.png" alt="Dockerfile.python single stage" width="800"/>
  <br>
  <em>Рисунок 2 - Создание Dockerfile.python с базовым образом python:3.12-slim и конструкцией COPY . .</em>
</p>

### 3. Создание .dockerignore
<p align="center">
  <img src="screenshots2/dockerignore.png" alt=".dockerignore файл" width="700"/>
  <br>
  <em>Рисунок 3 - Создание .dockerignore для исключения ненужных файлов</em>
</p>

### 4. Сборка и тестирование single stage образа
<p align="center">
  <img src="screenshots2/build-single.png" alt="Сборка single stage образа" width="900"/>
  <br>
  <em>Рисунок 4 - Сборка образа командой docker build -f Dockerfile.python -t test-app .</em>
</p>

<p align="center">
  <img src="screenshots2/curl-5000.png" alt="Проверка работы приложения" width="850"/>
  <br>
  <em>Рисунок 5 - Проверка работы приложения через curl http://localhost:5000 (получено предупреждение о неверном порте)</em>
</p>

### 5. Multistage сборка
<p align="center">
  <img src="screenshots2/dockerfile-multi.png" alt="Dockerfile.python multistage" width="800"/>
  <br>
  <em>Рисунок 6 - Изменение Dockerfile.python на multistage сборку</em>
</p>

<p align="center">
  <img src="screenshots2/build-multi.png" alt="Сборка multistage образа" width="900"/>
  <br>
  <em>Рисунок 7 - Сборка multistage образа test-app-multi</em>
</p>

<p align="center">
  <img src="screenshots2/docker-ps.png" alt="Запущенные контейнеры" width="1000"/>
  <br>
  <em>Рисунок 8 - Запущенные контейнеры: mysql-local, fastapi-app, test-app-multi</em>
</p>

### 6. Запуск через docker-compose
<p align="center">
  <img src="screenshots2/compose-yaml.png" alt="compose.yaml файл" width="800"/>
  <br>
  <em>Рисунок 9 - Создание compose.yaml для запуска MySQL и приложения</em>
</p>

<p align="center">
  <img src="screenshots2/compose-up.png" alt="Запуск docker compose" width="850"/>
  <br>
  <em>Рисунок 10 - Запуск стека командой docker compose up -d (контейнер mysql-test healthy)</em>
</p>

<p align="center">
  <img src="screenshots2/curl-8090.png" alt="Проверка порта 8090" width="800"/>
  <br>
  <em>Рисунок 11 - Проверка порта 8090 (nginx не запущен, поэтому connection refused)</em>
</p>

### 7. ✨ Запуск с venv (без Docker)
<p align="center">
  <img src="screenshots2/mysql-container.png" alt="Запуск MySQL контейнера" width="900"/>
  <br>
  <em>Рисунок 12 - Запуск MySQL в контейнере для локальной разработки</em>
</p>

<p align="center">
  <img src="screenshots2/venv-create.png" alt="Создание виртуального окружения" width="850"/>
  <br>
  <em>Рисунок 13 - Создание и активация виртуального окружения, установка зависимостей</em>
</p>

<p align="center">
  <img src="screenshots2/venv-run.png" alt="Запуск приложения через venv" width="900"/>
  <br>
  <em>Рисунок 14 - Запуск приложения через uvicorn на порту 5001 (подключение к БД успешно)</em>
</p>

<p align="center">
  <img src="screenshots2/venv-curl.png" alt="Проверка через curl" width="800"/>
  <br>
  <em>Рисунок 15 - Проверка работы приложения через curl (получено предупреждение)</em>
</p>

### 8. ✨ Добавление ENV переменной DB_TABLE
<p align="center">
  <img src="screenshots2/main-py-config.png" alt="Изменение конфигурации в main.py" width="850"/>
  <br>
  <em>Рисунок 16 - Добавление переменной db_table в секцию конфигурации</em>
</p>

<p align="center">
  <img src="screenshots2/export-db-table.png" alt="Установка DB_TABLE" width="800"/>
  <br>
  <em>Рисунок 17 - Установка переменной окружения DB_TABLE='my_custom_table'</em>
</p>

<p align="center">
  <img src="screenshots2/custom-table-start.png" alt="Запуск с кастомной таблицей" width="900"/>
  <br>
  <em>Рисунок 18 - Запуск приложения с DB_TABLE='my_custom_table' (таблица создана)</em>
</p>

<p align="center">
  <img src="screenshots2/custom-table-curl.png" alt="Проверка с кастомной таблицей" width="800"/>
  <br>
  <em>Рисунок 19 - Проверка работы с кастомной таблицей через curl</em>
</p>

### 9. Итоговые результаты
<p align="center">
  <img src="screenshots2/works-5002.png" alt="Успешная работа на порту 5002" width="850"/>
  <br>
  <em>Рисунок 20 - Успешная работа приложения на порту 5002 с кастомной таблицей</em>
</p>

<p align="center">
  <img src="screenshots2/all-containers.png" alt="Все контейнеры" width="1000"/>
  <br>
  <em>Рисунок 21 - Все созданные и запущенные контейнеры</em>
</p>

## Вывод
Все пункты задания выполнены:
- ✅ Создан fork репозитория
- ✅ Создан Dockerfile.python с образом python:3.12-slim и COPY . .
- ✅ Создан .dockerignore
- ✅ Протестирована single stage сборка
- ✅ Реализована multistage сборка
- ✅ ✨ Запуск с venv (без Docker)

- ✅ ✨ Добавлена ENV переменная DB_TABLE для управления названием таблицы
