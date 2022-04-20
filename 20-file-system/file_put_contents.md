# file_put_contents()
file_put_contents() записывает данные в файл. Принимает параметры: путь к файлу, данные. Функция возвращает число в байтах, равное контенту.

    // Получаем содержимое страницы сайта
    $file = file_get_contents("https://www.fdoctor.ru/vrach-kryuchenkova-nataliya-vladimirovna/");

    // Записываем содержимое сайта в файл
    file_put_contents("doctor.txt", $file);

Перезаписывает в файл:

    // Получаем содержимое страницы сайта
    $file = file_get_contents("https://www.fdoctor.ru/vrach-kryuchenkova-nataliya-vladimirovna/");
    $file2 = file_get_contents("https://www.fdoctor.ru/vrach-egorov-vladislav-mihailovich/");

    // Записываем содержимое сайта в файл
    file_put_contents("doctor.txt", $file);
    // Перезаписывает файл при добавлении нового контента
    file_put_contents("doctor.txt", $file2);

Чтобы данные в файл добавлялись, а не перезаписывались, нужно добавить параметр `FILE_APPEND`:

    // Записываем содержимое сайта в файл
    file_put_contents("doctor.txt", $file, FILE_APPEND);
    // Перезаписывает файл при добавлении нового контента
    file_put_contents("doctor.txt", $file2, FILE_APPEND);
