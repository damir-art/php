# Проектирование базы данных
Архитектура БД.

Данные можно хранить не только в одной таблице, но и в нескольких для оптимизации.

Распределяем данные по категориям:
- страны европы
- страны америки

Можно создать дополнительный столбец куда вписать категорию, а можно создать таблицу хранящую категории.

Таблица `countries`:
- category_id (ссылается на таблицу categories)

Таблица `categories`:
- id:   int, 2, primary, A_i
- name: varchar, 255