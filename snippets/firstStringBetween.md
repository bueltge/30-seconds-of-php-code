### firstStringBetween

Returns the first string there is between the strings from the parameter start and end.

```php
function firstStringBetween(string $haystack, string $start, string $end): string
{
    $char = strpos($haystack, $start);
    if (!$char) {
        return '';
    }

    $char += strlen($start);
    $len = strpos($haystack, $end, $char) - $char;

    return substr($haystack, $char, $len);
}
```

<details>
<summary>Examples</summary>

```php
firstStringBetween('This is a [custom] string', '[', ']'); // custom
```

</details>