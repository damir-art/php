# $_FILES
Загрузка файлов. Загруженный файл отправляется в `upload.php` для обработки. Файл загружается во временное хранилище с временным именем.

- index.php - форма для загрузки файлов `enctype="multipart/form-data"`
- upload.php - обработка загруженного файла

## index.php

    <form action="upload.php" method="POST" enctype="multipart/form-data">
        <p><input type="file" name="file" /></p>
        <p><button type="submit">Загрузить</button></p>
    </form>

## upload.php

    <?php
    echo "<pre>";
    print_r($_FILES);
    echo "</pre>";

Вывод загруженного файла:

    Array (
        [file] => Array (
            [name] => bmw.jpg,
            [type] => image/jpeg,
            [tmp_name] => D:\OpenServer\userdata\temp\upload\phpE56D.tmp,
            [error] => 0,
            [size] => 109438 ))

Доступ к данным, загруженного файла:

    $_FILES["file"]["type"]

## Загрузка файла

    // Загружаем файл из темпа на сайт
    move_uploaded_file($_FILES["file"]["tmp_name"], $_FILES["file"]["name"]);
    // Имя и путь можем изменять
    move_uploaded_file($_FILES["file"]["tmp_name"], "bmw3.jpg");

## Разные имена файлов
Делаем имена файлов разными, через временную метку.

    $fileName = time() . $_FILES["file"]["name"];
    move_uploaded_file($_FILES["file"]["tmp_name"], $fileName);

## Разное
- `enctype="multipart/form-data"` - форма поддерживает загрузку данных
