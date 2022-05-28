# Cookie

## Создание куки
Создаём куку, обновляем страницу и сморим её в браузере:

    setcookie("login", "ivan33"); // Создание куки имя/значение
    setcookie("pass", "turboglad");

## Доступ к куке

    echo "<pre>";
    print_r($_COOKIE);
    echo "</pre>";

    echo $_COOKIE["login"]; // ivan33

## Удаляем куку

    unset($_COOKIE["login"]);

При этом в браузере кука не удалится. Вот так можно удалить куку и в браузере.

    setcookie("login", NULL);
