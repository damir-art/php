# str_replace()
Поиск в строке.
- ищет подстроку в строке
- если найдет, то заменит другой подстрокой
- возвращает изменённую строку или не изменённую

Пример замены названия страницы сайта на своё:

    $search = "<title>Яндекс</title>";
    $replace = "<title>Гугл</title>";
    $subject = file_get_contents("https://site-name");
    str_replace($search, $replace, $subject);

    echo str_replace($search, $replace, $subject);;

Также может искать в массиве.

Пример замены `bb` кодов на HTML-теги:

    $str = "Всем привет, меня зовут [b]Иван[/b]";
    $str = str_replace("[b]", "<b>", $str);
    $str = str_replace("[/b]", "</b>", $str);

    echo $str;

## Заменяем несколько подстрок сразу
Чтобы заменить не одну, а множество подстрок сразу, нужно воспользоваться массивом.

    $str = "Всем привет, меня зовут [b]Иван[/b]";
    $search = array("[b]","[/b]");
    $replace = array("<b>","</b>");

    $str = str_replace($search, $replace, $str);

    echo $str;
