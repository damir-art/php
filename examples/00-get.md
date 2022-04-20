# $_GET
`http://php.loc/index.php?id=2` выводим данные конкретной страницы.

    $id = $_GET['id'];

    $posts = [
        [
            "id" => 0,
            "title" => "Заголовок 0",
        ],
        [
            "id" => 1,
            "title" => "Заголовок 1",
        ],
        [
            "id" => 2,
            "title" => "Заголовок 2",
        ],
        [
            "id" => 3,
            "title" => "Заголовок 3",
        ],
    ];

    foreach($posts as $post) {
        if($post["id"] == $id) {
            echo $post["title"];
            break;
        }
    }
