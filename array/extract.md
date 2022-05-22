# extract()
Преобразует элементы массива в переменные.

    $goroda = array(
        "moskva" => "Москва",
        "piter" => "Питер",
        "kazan" => "Казань",
    );

    $res = extract($goroda);

    echo $moskva; // Москва
