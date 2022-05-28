# Output buffering
Output buffering (буфер вывода) позволяет использовать `headers` даже после вывода какой-либо информации на странице.

Без буфера:

    PHP > Сервер

С буфером:

    PHP > Буфер > Сервер

Пока данные находятся в буфере, мы можем её менять, в том числе и заголовки.

Чтобы включить буферизацию нужно изменить файл `php.ini` или вносить изменения на каждой странице где используется буферизация. 

Чтобы проверить включен ли буфер выведите информацию о PHP `phpinfo()` ищите строку `output_buffering`.

## ob_start()
Включаем буферизацию на конкретной странице.

    ob_start() // запуск буфера вывода
    
    PHP-код

    ob_end_flush() // остановка буфера вывода

`ob_start()` - должен располагаться перед любым контентом