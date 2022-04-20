# $_COOKIE
Пример кода авторизации с использованием кук.

Приложение состоит из файлов:
- `users.php` массив "База данных" с пользователями, для авторизации
- `index.php` форма для авторизации
- `login.php` код проверки авторизации
- `profile.php` профиль куда переадресовывается пользователь после удачной авторизации
- `logout.php` очищающий куки профиля 

## user.php
База данных

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
Страница с формой

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
Проверяем введённые данные пользователем

    $users = require_once "users.php"; // массив содержащий данные из базы

    $login = $_POST["login"];
    $password = $_POST["password"];

    // Без кук
    // foreach($users as $user) {
    //     if($user["login"] == $login && $user["password"] == $password) {
    //         echo "Авторизация";
    //         break;
    //     } else {
    //         echo "Отказ";
    //         break;
    //     }
    // }

    // Добавляем куки
    foreach($users as $user) {
        if($user["login"] == $login && $user["password"] == $password) {
            echo "Авторизация";
            setcookie("login", $user["login"]);
            header("Location: profile.php"); // Переадресация на страницу профиля
            break;
        } else {
            echo "Отказ";
            break;
        }
    }

## profile.php
Профиль пользователя, куда редиректит пользователя после проверки, там же находится кнопка выхода очищающая куки.

    <h1>Добро пожаловать <?php echo $_COOKIE["login"]; ?></h1>
    <p>
        <a href="logout.php">Выход</a> <!-- Очистка кук -->
    </p>

## logout.php
Очистка кук

    unset($_COOKIE["name"]);
    setcookie("name", NULL);
    header("Location: index.php");
