# Тернарный оператор

    $names = ["Иван", "Петр", "Сидор"];
    $find = "Иван";

    $result = in_array($find, $names); // Ищем $find в массиве $names, вернет bool

    if ($result) {
        echo "Найдено";
    } else {
        echo "Не найдено";
    }

Вместо `if ... else` можно использовать тернарный оператор:

    $result = in_array($find, $names) ? "Найдено" : "Не найдено";
    echo $result; // Найдено
