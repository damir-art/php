# UPDATE
Обновление данных.

    // Обновление записи в БД
    $query = "UPDATE `countries` SET `name` = 'Великобритания' WHERE `countries`.`id` = 3";
    $mysqli->query($query);

После SET пишем имя столбца и изменённое значение. Здесь `countries`.`id` можно заменить на `id`.
