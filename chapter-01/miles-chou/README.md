
## Parse

書中有提到幾使用 `parseInt()` 成數值的方法 (中文 P.24)

```javascript
var someString = "09";

var usingParse = parseInt(someString, 10); // 注意：如果沒加基數 09 會認為是 8 進位，因為 09 是不合法的，會轉成 0
var usingLiteral = +someString;
var usingNumber = new Number(someString); // 物件
```

如果是要轉成文字也有幾種建議的方法如：

```javascript
var someNumber = 999;

var usingLiteral = '' + someNumber;
var usingConcat = ''.concat(someNumber);    // 字串合併時，可以強制轉型
var usingArrayJoin = [someNumber].join(''); // 同上
```

## Switch

Java 或 PHP 在使用 switch 時，都會建議無論如何都要有 `default` 。如：

```php
<?php

switch ($someCase)
{
    case 1:
        echo 'This is Case 1';
        break;
    case 2:
        echo 'This is Case 2';
        break;
    default:
        throw new Exception('Undefine Case');
}
```

這用在列舉的時候非常好用，最常發生的問題會是新增了列舉，但相對應的判斷（指 `switch` ）並沒有新增，這時就會丟例外提醒開發者要修改對應的程式碼。
