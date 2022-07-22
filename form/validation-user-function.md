# Пользовательская функция валидации
Создаём функцию с помощью которой можно проверить любую форму на нашем сайте. Можно делать сколько угодно функций проверок валидаций, рассмотрим три:

    // Поле не должно быть пустым
    function has_presence($value) {
        return isset($value) && $value !== "";
    }

    // Количество отправленных знаков
    function has_max_length($value, $max) {
        return strlen($value) <= $max;
    }

    // Проверяем есть ли массиве значение $value
    function has_inclusion_in($value, $set) {
        return in_array($value, $set);
    }

    // Если массив не пустой, то выводим список ошибок
    function form_errors($errors = array()) {
        if(!empty($errors)) {
            $output = "<div class='error'>";
            $output .= "Пожалуйста исправьте ошибки:";
            $output .= "<ul>";
            foreach($errors as $key => $error) {
                $output .= "<li>{$error}</li>";
            }
            $output .= "</ul>";
        } else {
            $output = "Массив с ошибками пуст";
        }
        return $output;
    }

    $errors = array();

    // Проверяем переменную
    // $username = trim($_POST["username"]);
    $username = trim("");

    if(!has_presence($username)) {
        $errors["username"] = "Заполните поле имя!";
    }

    echo form_errors($errors);
