# include, require
Включаемые файлы, позволяют не повторяться и написать код, например функцию, лишь один раз. Позволяют упорядочить код, добавлять частоиспользуемый код из одного места и мн др.

- include()
- include_once()
- require() - покажет ошибку если файл не найден
- require_once()

Файл с функциями должен подключаться перед `header.php`, пример файла `index.php`:

    <?php
        require_once "functions.php";
        require_once "header.php";
    ?>

    <?php echo get_name("Иван"); ?>

    <?php require_once "footer.php"; ?>

**include** и другие аналогичные функции отключают режим PHP, поэтому внутри подключаемых файлов, например `functions.php` нужно использовать `<?php ?>`:

    <?php
    function get_name($name) {
        return "Ваше имя $name!";
    }


## Старая запись

Используются для подключения к PHP-файлу, других PHP-файлов.

В `index.php` помещаем:

    include "test.php";
    require "test.php";
    echo sum(3, 8);

В `test.php` помещаем:

    function sum($a, $b) {
        return $a + $b;
    }

Разница между include и require, если файл подключаемый через require отсутствует то следующий после него код не сработает.

**require_once** - позволяет 1 файл загрузить на страницу 1 раз

## Примеры
В test.php могут быть не только функции но и например возврат массива:

    return [
        "name" => "Иван",
        "sub_name" => "Иванов",
    ];

А в индекс можем записать:

    $arr = require_once "test.php";
    echo $arr["name"]; // Иван
