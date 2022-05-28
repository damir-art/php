# substr()
Ищет подстроку из строки.

    // Функция ищет теги на странице,
    // нужно доработать, title ищет, остальные теги нет
    function get_tag($url, $tag) {
        $html = file_get_contents($url);
        $start = mb_strpos($html, "<" . $tag . ">" );
        $end = mb_strpos($html, "</" . $tag . ">");
        $tag_len = mb_strlen($tag);
        $length = $end - $start + $tag_len + 3;
        $tag = htmlspecialchars(mb_substr($html, $start, $length));

        return $tag;
    }

    $url = "https://site-name";
    $tag = "title";
    echo get_tag($url, $tag);
