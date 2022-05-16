# DELETE
Удаление записи из БД.

    $query = "DELETE FROM `countries` WHERE `countries`.`id` = 3";
    $mysqli->query($query);

Здесь `countries`.`id` можно заменить на `id`.
