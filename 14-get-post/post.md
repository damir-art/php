# $_POST
Чтобы массив $_POST заполнился данными из формы у элементов форм должны быть атрибуты `name`. Данные пост запроса обычно сохраняются в базу данных.

Создаём форму `index.php`:

    <form method="POST" action="test.php">
        <p>
            Имя: <input type="text" name="name" /></p>
        <p>
            Фамилия: <input type="text" name="sur_name" /></p>
        <p>
            Возраст: <input type="number" name="age" /></p>
        <button type="submit">Отправить</button>
    </form>

Создаём PHP-код `test.php`:

    echo "<pre>";
    print_r($_POST);
    echo "</pre>";

    $name = $_POST["name"];
    $sur_name = $_POST["sur_name"];
    $age = $_POST["age"];
