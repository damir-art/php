# array_key_exists()
Проверяет ключ/индекс на существование.

    $names = array("Иван", "Пётр", "Сидор");

    echo array_key_exists(0, $names); // 1
    echo array_key_exists(3, $names); // Пусто
