# file_get_contents()
file_get_contents() - читает содержимое файла. В качестве параметра принимает путь к файлу.

    // Читаем содержимое файла
    $file = file_get_contents("text.txt");
    
    // Выводим содержиме файла
    echo $file;

Данная функция может еще читать содержимое сайтов.

    // Читаем содержимое сайта
    $file = file_get_contents("https://site-name");

    // Выводим содержимое сайта
    echo $file;

    // Выводим содержимое сайта в виде тегов
    echo htmlspecialchars($file);

    // Выводим содержимое файла подставляя br вместо переноса строки
    echo nl2br($file);
