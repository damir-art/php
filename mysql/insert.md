# INSERT
Вставка записи в БД:

    $query = "INSERT INTO `countries` (`id`, `name`, `capital`, `domain`) VALUES (NULL, 'Германия', 'Берлин', '.de')";
    $mysqli->query($query);

Имена столбцов `(id, name, capital, domain)` можно не писать.
