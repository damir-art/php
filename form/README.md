# Формы
Создаём формы для отправки данных. Данные из формы помещаются в суперглобальную переменную `$_POST` в виде ассоциативного массива.

Создаём форму в `index.php`:

    <form action="form_result.php" method="post">
        <input type="text" name="username" value="" /><br />
        <input type="password" name="password" value="" /><br />
        <button type="submit" name="btn">Отправить</button>
    </form>

Обрабатываем форму в `form_result.php`:

    echo "<pre>";
    print_r($_POST);
    echo "</pre>";

Если находясь в `form_result.php` обновить страницу, то отправится post-запрос, если кликнуть по адресной строке и нажать `Enter` то отправится get-запрос.

Присваиваем переменным значения полей формы:

    $username = $_POST["username"];
    $password = $_POST["password"];

    echo "{$username}: {$password}";

В отличии от get-запросов, post-данные не нуждаются в кодировании и декодировании.

## Проверка на заполненность
Проверяем значение полей форм на заполненоость. Если поле не заполнено то вставляем значение по-умолчанию.

    $username = isset($_POST["username"]) ? $_POST["username"] : "Введите имя";
    $password = isset($_POST["password"]) ? $_POST["password"] : "Введите пароль";

Проверяем по нажатию на кнопку:

    if(isset($_POST["btn"])) {

    }
