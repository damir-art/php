# Одностраничная обработка формы
Форма и код её обработки располагаются на одной странице.

Преимущества:
- всё в одном месте
- обработка ошибок
- заполнение

Форма должна отправлять данные на свою же страницу:

    // Разместить код в начале страницы
    if(isset($_POST["btn"])) {
        // нажата кнопка
        echo "Форма отправлена";
    } else {
        // нажат enter на адресной строке (get-запрос)
        echo "Форма не отправлена";
    }
    echo "<hr />";

    echo "<pre>";
    print_r($_POST);
    echo "</pre>";

    <form action="index.php" method="post">
        <input type="text" name="username" value="" /><br />
        <input type="password" name="password" value="" /><br />
        <button type="submit" name="btn">Отправить</button>
    </form>

Присваиваем переменным значения из формы, при авторизации переходим на другую страницу:

    if(isset($_POST["btn"])) {
        $username = $_POST["username"];
        $password = $_POST["password"];
        if($username=="damir" && $password=="123") {
            header("Location: http://ya.ru");
            exit;
        } else {
            $message = "Произошла ошибка";
        }
    } else {
        $username = "";
        $message = "Войдите на сайт";
    }

    <?php echo $message; ?>

    <form action="index.php" method="post">
        <input type="text" name="username" value="<?php echo htmlspecialchars($username); ?>" /><br />
        <input type="password" name="password" value="" /><br />
        <button type="submit" name="btn">Отправить</button>
    </form>
