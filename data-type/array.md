# Массивы
Массив тоже что переменная только в отличии от неё содержит сразу несколько значений. Массивы можно создавать двумя способами, с помощью функции `array()` или с помощью квадратных скобок `[ ]`.

    $names = array("Иван", "Петр", "Сидор");
    $names = ["Иван", "Петр", "Сидор"];

Вывод массива:

    echo "<pre>";
    print_r($names);
    echo "</pre>";

Вывод элемента массива:

    echo $names[0]; // Иван
    echo $names{0}; // Иван

Добавление элемента в конец массива:
    
    $user[] = "Вася";

Изменение элемента массива:

    $names[1] = "Орлов";

## Ассоциативные
Ассоциативные массивы имеют пользовательские ключи.

    $user = array(
        "name" => "Иван",
        "sur_name" => "Петров",
        "age" => 27,
    );

    echo $user["name"]; // Иван

Ключи могут быть числами.

## Вложенные (многомерные) массивы
Обычные и ассоциативные массивы можно вкладывать друг в друга:

    $user = array(
        "name" => "Иван",
        "sur_name" => "Петров",
        "age" => 27,
        "skill" => array("HTML", "CSS", "JavaScrpt", "PHP")
    );

    echo $user["skill"][3]; // PHP

## in_array()
Проверяем имеется ли элемент в массиве.

    var_dump(in_array("Иван", $names)); // true

Обычно используется в условиях.

## unset()
Удаляем элемент из массива.

    unset($names[1]);

Останется 2 элемента их индексы не пересчитаются. Также можно удалять и переменные.

## Указатель массива
Указатели понадобятся при работе с MySQL. При работе с foreach указатель перемещается по массиву.

    $arr = array("Москва", "Берлин", "Пекин");
    echo current($arr); // Москва
    next($arr);
    next($arr);
    echo current($arr); // Пекин
    prev($arr);
    echo current($arr); // Берлин
    echo reset($arr); // Москва, перемещает курсор к первому элементу
    echo end($arr); // Пекин, перемещает курсор к последнему элементу

Создадим аналог foreach с помощью while и указателей:

    while($ar = current($arr)) {
        echo $ar . "<br />";
        next($arr);
    }