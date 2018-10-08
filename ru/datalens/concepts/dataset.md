# Датасет

_Датасет_ описывает набор данных. Источником данных для датасета может быть только одна таблица.
При создании датасета можно определить измерения и показатели, переименовать поля, указать функцию агрегации для показателей.

Датасет содержит следующие поля данных:

- **Измерение**. Группирует данные. Например: город, тип устройства, операционная система.
- **Показатели**. Содержит числовые значения. Например: сумма кликов, количество переходов. 

Датасет может работать с источником данных в двух режимах:

- **Директ** — все запросы исполняются на стороне источника.
- **Единовременная загрузка** — данные загружаются в хранилище DataLens единовременно. Все последующие запросы обрабатываются на загруженных данных. Чтобы синхронизировать хранилище DataLens с источником, данные можно загрузить повторно.

#### См. также
- [[!TITLE]](../operations/dataset/create.md)