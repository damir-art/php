# array_intersect()
array_intersect() - сравнивает массивы, противоположен array_diff().

    $names = array("Иван", "Пётр", "Сидор");
    $names2 = array("Иван", "Пётр", "Сидор2");

    print_r(array_intersect($names, $names2)); // Иван, Пётр
