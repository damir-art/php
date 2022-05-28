# HTTP-запросы
Работаем с HTTP-запросами: get, post и т.д.

Три способа отправить запрос на сервер:
- URL, ссылки `GET`
- формы `POST`
- куки `COOKIE` (способ получения информации, на каждый запрос)

## Динамические ссылки

    <?php
        $second_page = "Вторая страница";
        $id = 2;
    ?>
    <a href="index2.php?id=<?php echo $id; ?>"><?php echo $second_page; ?></a>

## Методы HTTP-запроса
$_GET, $_POST - методы HTTP запроса. Используются для отправки данных, например сохранение в БД, получения из БД и т.п.

- $_GET - получение данных из БД
- $_POST - сохранение данных в БД
- $_FILES - работа с файлами

## Request - Response
Запрос - ответ.

Браузер (найди файл) > Сервер (находит файл, если это .php, то передаёт PHP) > PHP (если нужно, то обращается к БД) > БД > PHP > Код превращается в HTML > Браузер

## Разное
- $_GET, $_POST - суперглобальные переменные, зарезервированы в языке