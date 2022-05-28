# Циклы
Циклы позволяют выполнять один и тот же код многократно.

## for

    $names = ["Иван", "Петр", "Сидор", "Андрей", "Роман"];

    for($i = 0; $i < count($names); $i++) {
        echo $names[$i] . "<br />";
    }

## while

    $i = 0;
    while ($i < count($names)) {
        echo $names[$i] . "<br />";
        $i++;
    }

## do ... while

## foreach
Работают с массивами, количество итераций зависит от количества элементов.

    // Значение
    foreach ($names as $elem ) {
        echo $elem . "<br />";
        // echo $elem["title"] . "<br />"; для многомерных ассоциативных
    }

    // Ключ значение
    foreach ($names as $key => $val ) {
        echo $val . "<br />";
    }

## continue
continue - пропустить итерацию

    foreach ($names as $elem ) {
        if (!$elem["public"]) continue; // пропустить если пост не опубликован
        echo $elem["title"] . "<br />";
    }

Влеженные циклы: continue(2), выход из внутреннего цикла на уровень выше.

## break
break - завершает цикл

    $countPost = 0;
    foreach ($names as $elem ) {
        if ($countPost == 2) break; // закончить выводить посты если их 2
        echo $elem["title"] . "<br />";
        $countPost++;
    }

Влеженные циклы: break(2), выход из внутреннего цикла на уровень выше.
