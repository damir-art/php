# compact()
Создаёт массив из переменных.

    $moskva = "Москва";
    $piter = "Питер";
    $kazan = "Казань";

    $res = compact("moskva", "piter", "kazan");

    echo "<pre>";
    print_r($res);
    echo "</pre>";

Получаем ассоциативный массив:

    Array(
        [moskva] => Москва
        [piter] => Питер
        [kazan] => Казань
    )
