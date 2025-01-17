# Структура проекта 
 в `models/` содержатся все ml модели и файлы для тестирования и запуска. На текущий момент присутствует только одна модель.
- `real_estate_model/` содержит весь основной код пакета: `train.py`, `predict.py`, `config.py`. Также в этой папке находятся датасеты и обученные веса`datasets/` и `trained_models/` соответственно . 
- `requirements/` содержит все необходимые зависимости для использования и тестирования.
- `tests/` содержит код тестов
- `webapp/` содержит код веб-интерфейса.


# Использование

Код запускается и тестируется при помощи tox. Параметры обучения и предсказания находятся в `models/real_estate_model/config.yml`.
Для работы требуется python 3.8.2

## Обучение

Перед началом обучения:

- Нужно скачать [датасет](https://www.kaggle.com/datasets/mrdaniilak/russia-real-estate-20182021) и прописать абсолютный путь к csv-файлу в конфиге в поле `dataset` 
- По желанию настроить другие параметры обучения.

Обучение запускается командой:

```
tox -e train
```


## Предсказание

Для предсказания в конфиге указывается путь к весам обученной модели в поле `predict_model` и список переменных, на которых она обучалась `predictors`.
Валютой предсказанной стоимости является рубль. Запуск производится командой:

```
tox -e predict
```


# Веб-приложение

Основной функционал запускается командой:

```
tox -e app
```

# Датасет

Для обучения использовался датасет:
https://www.kaggle.com/datasets/mrdaniilak/russia-real-estate-20182021