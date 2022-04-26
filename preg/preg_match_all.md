# preg_match_all()
Возвращает массив из количества вхождений.

    preg_match_all("~a~", "It rains cats and dogs.", $m);

    echo "<pre>";
    print_r($m);
    echo "</pre>";

    Array(
        [0] => Array(
            [0] => a
            [1] => a
            [2] => a
        )
    )
