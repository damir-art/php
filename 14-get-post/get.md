# $_GET
Длина URL ограничена 1024 символами.

    print_r($_GET); // Array()

Пишем параметры URL-запроса:

    http://php.loc/index.php?par=111&par2=222

    print_r($_GET); // Array ( [par] => 111 [par2] => 222 ) 

После адресной строки, указываем `?par=111&par2=222` знак вопроса и параметры через амперсанд.

    http://php.loc/index.php?name=Иван&sub_name=Иванов

    Array ( [name] => Иван [sub_name] => Иванов )
