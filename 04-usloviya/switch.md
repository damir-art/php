# switch
Аналог множественного `elseif`, где нужно проверять одну переменную на различные значения.

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
