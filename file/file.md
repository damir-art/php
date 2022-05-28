# file()
Читает содержимое файла в массив. Каждая строка это элемент массива.

Файл `text.txt` содержит:

    hello 0
    hello 1
    hello 2

Читаем файл:

    $file = file("hello.txt");

    echo "<pre>";
    print_r($file);
    echo "</pre>";

Не добавлять новую строку к концу каждого элемента массива `FILE_IGNORE_NEW_LINES`:

    $file = file("text.txt", FILE_IGNORE_NEW_LINES);

Также есть флаг пропускающий пустые строки, можно его добавить через `|`.
