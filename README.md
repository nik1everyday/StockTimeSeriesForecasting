# StockTimeSeriesForecasting
### <a href="/designdoc/designdoc.md">Дизайн-документ проекта</a>

## Описание проекта
Проект по прогнозированию цен на нефть нацелен на разработку системы, которая способна предсказывать будущие цены на нефть.

Используя методы машинного обучения, а также анализ временных рядов, производится обучение моделей, включая CatBoost, ARIMA, Prophet и другие. 

Основной фокус системы — предоставить пользователям точные и актуальные прогнозы, а веб-сервис, построенный с использованием FastAPI и React, обеспечивает удобный доступ к этой информации. 

## Как запустить проект
Чтобы добавить этот репозиторий на свой локальный компьютер, вы можете выполнить следующие действия:

**Шаг 1.** Склонируйте репозиторий, выполнив следующую команду в терминале:
```bash
git clone https://github.com/nik1everyday/StockTimeSeriesForecasting.git
```

**Шаг 2.** Перейдите в каталог репозитория:
```bash
cd StockTimeSeriesForecasting
```
**Шаг 3.** Установите необходимые зависимости с помощью pip:
```bash
pip install -r requirements.txt
```
**Шаг 4.** Запустите сервис, вызвав следующую команду в терминале:
```bash
uvicorn service.api.app:app --port 8000 --reload
```
Сервис будет доступен на локальной машине по адресу http://127.0.0.1:8000. Если вы хотите, чтобы ваш сервис был доступен в интернете, выполните **Шаг 5** после запуска сервиса на локальной машине: 

**Шаг 5.**
```bash
cloudflared tunnel --url http://127.0.0.1:8000
```


## Структура проекта

- **designdoc/**
  - `designdoc.md` - дизайн-документ проекта

- **notebooks/**
  - `ARIMA_model.ipynb` - ноутбук с моделью ARIMA
  - `baseline_exp_smoothing.ipynb` - ноутбук с базовой экспоненциальной сглаживающей моделью
  - `EDA.ipynb` - ноутбук с анализом данных (Exploratory Data Analysis)
  - `grad_boost_model.ipynb` - ноутбук с моделью градиентного бустинга
  - `GRU_model.ipynb` - ноутбук с моделью GRU
  - `SARIMA_model.ipynb` - ноутбук с моделью SARIMA

- **service/**
  - **api/**
    - `__init__.py` - инициализационный файл пакета API
    - `app.py` - основной файл с FastAPI приложением
    - `views.py` - файл с представлениями API
  - **config/**
    - `__init__.py` - инициализационный файл пакета конфигурации
    - `config.yaml` - файл с конфигурацией
  - **static/**
    - `static/` - директория со статическими ресурсами для веб-интерфейса
      - `asset-manifest.json`
      - `favicon.ico`
      - `index.html` - HTML-страница для веб-интерфейса
      - `logo192.png`
      - `logo512.png`
      - `manifest.json`
      - `robots.txt`
    - `__init__.py` - инициализационный файл пакета статических ресурсов

- **src/**
  - `__init__.py` - инициализационный файл пакета исходного кода
  - `load_data.py` - модуль для загрузки данных
  - `predict_data.py` - модуль для обучения и предсказания данных

- `.gitignore` - файл для игнорирования файлов и директорий при работе с Git
- `pyproject.toml` - файл с конфигурацией Poetry
- `requirements.txt` - файл с зависимостями
- `README.md` - файл с описанием проекта и инструкциями по запуску


## Команда
Никита Борисов – `@nik1everyday` <br>
Евгений Бакаев – `@evalyev`
