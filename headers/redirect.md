# Переадресация
Переадресация страниц.

    header("Location: login.php"); // статус 302
    exit; // чтобы не отсылать данные которые идут после редиректа

Создадим функцию обрабатывающую редирект и в зависимости от параметра get-запроса перенаправляющую по определённому адресу:

    function redirect_to($url_path) {
        header("Location: " . $url_path);
        exit;
    }

    $logged_in = $_GET["logged_in"];
    if($logged_in == "1") {
        redirect_to("login.php");
    } else {
        redirect_to("exit.php");
    }
