## include, require
Используются для подключения к PHP-файлу, других PHP-файлов.

В `index.php` помещаем:

    include "test.php";
    require "test.php";
    echo sum(3, 8);

В `test.php` помещаем:

    function sum($a, $b) {
        return $a + $b;
    }

Разница между include и require, если файл подключаемый через require отсутсвует то следующий после него код не сработает.

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
