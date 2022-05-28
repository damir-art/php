# switch
Аналог множественного `elseif`, где нужно проверить значение переменной, на равенство `==` с другими значениями. Обычно проверяют строки.

    $color = "green";

    switch($color) {
        case "red":
            echo "Красный";
            break;
        case "green":
            echo "Зелёный";
            break;
        default:
            echo "Черный";
            break;
    }
