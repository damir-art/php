# null
null и empty.

- `null` - отсутствие значения
- `is_null()` - проверяем, является ли нулом

Примеры:

    $a = null;

    is_null($a) // 1
    is_null($b) // 1 и появление предупреждения

## empty()
empty() возвратит true при: "", 0, false, null, array(), "0", 0.0
