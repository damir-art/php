# trim()
Удаляет пробелы с начала или конца строк. Помимо пробелов также по-умолчанию удаляет `\t,\n,\r,\0,\x0B`. Может удалить любой другой символ если его указать.

    echo $str . $str2 . "<br />"; // Иван Иванович
    echo trim($str) . trim($str2); // ИванИванович
