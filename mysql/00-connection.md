# Подключение к БД

    <style>
    table {
        font-family: Arial;
        border-collapse: collapse;
    }
    td,th {
        padding: 4px 16px;
        border-bottom: 1px solid #333;
    }
    </style>

    <?php
    // Подключаемся к БД
    $mysqli = new mysqli('localhost', 'root', '', 'country');

    // Выводим сообщение, если при подключении возникла ошибка
    if(mysqli_connect_errno()) {
        printf('Ошибка соединения с БД', mysqli_connect_error() );
        exit();
    }

    // Если есть проблема с кодировкой
    // $mysqli->set_charset('utf8');

    // Вставка записи в БД
    // $query = "INSERT INTO `countries` (`id`, `name`, `capital`, `domain`) VALUES (NULL, 'Германия', 'Берлин', '.de')";
    // $mysqli->query($query);

    // Обновление записи в БД
    // $query = "UPDATE `countries` SET `name` = 'Великобритания' WHERE `countries`.`id` = 3";
    // $mysqli->query($query);

    // Удаление записи из БД
    // $query = "DELETE FROM `countries` WHERE `countries`.`id` = 3";
    // $mysqli->query($query);


    // Создаём запрос к БД (выбрать всё из таблицы countries)
    $query = $mysqli->query('SELECT * FROM `countries`');

    // Перебираем результат $query построчно
    echo '<table>';
    echo '<tr><th>№</th><th>Название</th><th>Столица</th><th>Домен</th></tr>';
    while($row = mysqli_fetch_assoc($query)) {
        echo '<tr>';
        echo '<td>' . $row['id']      . '</td>';
        echo '<td>' . $row['name']    . '</td>';
        echo '<td>' . $row['capital'] . '</td>';
        echo '<td>' . $row['domain']  . '</td>';
        echo '</tr>';
    }
    echo '</table>';

    // Закрываем БД
    $mysqli->close();

    // echo '<pre>';
    // print_r($row);
    // echo '</pre>';
