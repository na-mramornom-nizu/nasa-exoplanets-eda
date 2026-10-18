# NASA Exoplanets — разведочный анализ данных

Учебный проект по интеллектуальному анализу данных. В [ноутбуке](NASA_Exoplanets_EDA.ipynb) проверяются три гипотезы о связи метода обнаружения с радиусом и орбитальным периодом экзопланет, а также о связи радиуса планеты с температурой звезды.

## Как запустить

1. Создайте окружение Python 3.11+ и установите зависимости: `python -m pip install -r requirements.txt`.
2. Откройте `NASA_Exoplanets_EDA.ipynb` в Jupyter и выберите это окружение как ядро.
3. Запустите все ячейки по порядку. Файл `exoplanets.csv` уже лежит рядом с ноутбуком. Чтобы использовать другую выгрузку, измените переменную `DATA_PATH` в первой ячейке кода.

## Данные

Источник — [NASA Exoplanet Archive, таблица PSCompPars](https://exoplanetarchive.ipac.caltech.edu/docs/API_PS_columns.html), снимок загружен **18 октября 2026 года**. Таблица содержит одну строку на планету; в проекте оставлены только нужные восемь полей. [Документация NASA TAP](https://exoplanetarchive.ipac.caltech.edu/docs/TAP/usingTAP.html) объясняет способ выгрузки.

Для обновления данных можно открыть запрос и сохранить ответ под именем `exoplanets.csv`:

```text
https://exoplanetarchive.ipac.caltech.edu/TAP/sync?query=select%20pl_name,pl_bmasse,pl_rade,pl_orbper,discoverymethod,disc_year,st_teff,disc_facility%20from%20pscomppars&format=csv
```

Цифры в текстовых выводах соответствуют приложенному снимку; после обновления CSV их нужно пересчитать. Частоты открытий зависят от методов наблюдения и не описывают истинное распределение всех экзопланет.
