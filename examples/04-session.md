# $_SESSION
Пример кода авторизации с использованием сессий.

Приложение состоит из файлов:
- `users.php` массив "База данных" с пользователями, для авторизации
- `index.php` форма для авторизации
- `login.php` код проверки авторизации
- `profile.php` профиль куда переадресовывается пользователь после удачной авторизации
- `logout.php` удаляет данные из сессии

## users.php

    return [
        [
            "id"        => 0,
            "login"     => "Логин_0",
            "password"  => "Пароль_0",
            "email"     => "Почта_0",
        ],
        [
            "id"        => 1,
            "login"     => "Логин_1",
            "password"  => "Пароль_1",
            "email"     => "Почта_1",
        ],
        [
            "id"        => 2,
            "login"     => "Логин_2",
            "password"  => "Пароль_2",
            "email"     => "Почта_2",
        ]
    ];

## index.php

    <form action="login.php" method="POST">
        <p>
            Логин:<br />
            <input type="text" name="login" /></p>
        <p>
            Пароль:<br />
            <input type="password" name="password" /></p>
        <button type="submit">Отправить</button>
    </form>

## login.php

    session_start();
    $users = require_once "users.php"; // массив содержащий данные из базы

    $login = $_POST["login"];
    $password = $_POST["password"];

    foreach($users as $user) {
        if($user["login"] == $login && $user["password"] == $password) {
            echo "Авторизация";
            $_SESSION["login"] = $user["login"]; // Заносим данные из формы в сессию
            header("Location: profile.php");     // Переадресация на страницу профиля
            break;
        }
    }

    echo "Отказано в доступе!";

## profile.php

    <?php
    session_start();
    ?>

    <h1>Добро пожаловать <?php echo $_SESSION["login"]; ?></h1>
    <p>
        <a href="logout.php">Выход</a>
    </p>

## logout.php

    session_start();
    $_SESSION = array(); // Очищает все данные сессии
    session_destroy();
    header("Location: index.php");
