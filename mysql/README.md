# MySQL
Создание БД в PHPMyAdmin.

Создание базы данных:
- имя базы, utf8_general_ci

Создание таблицы:
- имя таблицы, количество столбцов
- id:      int,     3,  primary, a_i
- name:    varchar, 255
- capital: varchar, 255
- domain:  varchar, 4

Вставить запись:

    INSERT INTO `countries` (`id`, `name`, `capital`, `domain`) VALUES (NULL, 'США', 'Вашингтон', '.us');

Удалить запись:

    DELETE FROM `countries` WHERE `countries`.`id` = 3;

Обновить запись:

    UPDATE `countries` SET `id` = '3' WHERE `countries`.`id` = 4;

## Функции MySQL
- `Now()` - вставляем текущую дату
