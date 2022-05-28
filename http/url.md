# Кодирование URL-запроса `urlencode()`
Например как в значении передать символ `&`, но чтобы он не считался разделителем параметров. Есть зарезервированный список символов для передачи в URL, который нужно кодировать:

    ! # $ % & ' ( ) * + , / : ; = ? @ [ ]

Кодирование, знак процента и шестнадцатеричное число: `%FF`, пробелы станут плюсом: `+`. `rawurlencode()` пробелы переводит в `%20`.

    <?php
        $second_page = "Вторая страница";
        $id    = 2;
        $title = urlencode("Заголовок & страницы");
        $descr = "Описание страницы";
    ?>

    <a href="index2.php?id=<?php echo $id; ?>&title=<?php echo $title ?>&descr=<?php echo $descr ?>"><?php echo $second_page; ?></a>

Можно создать одну переменную `$url` через присваивание конкатенации `.=` и работаь потом с ней.

Помимо кодирования `urlencode()`, есть еще декодирование `urldecode()`. Обычно декодирование происходит автоматически.

Когда использовать `urlencode()`, а когда `rawurlencode()`:
- rawurlencode - в URL до знака вопроса `?`
    - путь к файлу
    - AJAX-запрос
- urlencode - в URL после знака вопроса `?`

Пример с `urlencode()` и `rawurlencode()`:

    $url_path = "/category/page.php"; // путь к файлу, пробелы должны быть заменены на %20
    $par =  "Символы HTML < >";
    $par2 = "Остальные символы & ? #";
    $lnk_txt = "<Нажать>"; // текст ссылки

    $url =  "http://localhost.loc/";
    $url .= rawurlencode($url_path);
    $url .= "?" . "par=" . urlencode($par);
    $url .= "&" . "par2=" . urlencode($par2);

    <a href="<?php echo htmlspecialchars($url); ?>">
        <?php echo htmlspecialchars($lnk_txt); ?>
    </a>

## Кодирование HTML
Кодирование зарезервированных символов в HTML, в мнемоники:

    <    >    &     "
    &lt; &gt; &amp; &quot;

- htmlspecialchars() - кодирование `<`, `>`, `&`, `"`
- htmlspecialchars_decode() - декодирование обычно происходит автоматически
- htmlentities() - в мнемоники переводятся все символы для которых есть эквивалент
