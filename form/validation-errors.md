# Вывод ошибок валидации
Вывод ошибок валидации дружелюбное пользователю.

Помещаем все ошибки в ассоциативный массив и все ошибки показываем пользователю, при попытке отправить форму:

    $errors = array();

    $value = trim("");
    if(!isset($value) || $value === "") {
        $errors["value"] = "Введите данные!";
    }

    // Выводим массив с ошибками
    // echo "<pre>";
    // print_r($errors);
    // echo "</pre>";

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

    echo form_errors($errors);

    $error = array();

## Разное
Проверяет существует ли этот ключ в массиве с ошибками:

    if(array_key_exists($errors, "name")) {
        echo "<span class='error__field'>&lt;&lt;</span>";
    }
