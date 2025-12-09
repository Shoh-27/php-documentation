## 2. Asosiy Sintaksis
PHP kodini yozishdan oldin, uning asosiy sintaksisini tushunish kerak. Bu bo'limda siz o'zgaruvchilar, ma'lumot turlari, operatorlar va asosiy funksiyalarni o'rganasiz.

## 2.1. PHP kodini yozish
PHP kodi har doim <?php bilan boshlanadi va HTML ichida yoki alohida PHP faylida yozilishi mumkin.

## Misol 1: Oddiy PHP fayl
```
    <?php
    echo "Salom, Dunyo!";
```

## Misol 2: HTML ichida PHP

```
   <!DOCTYPE html>
    <html>
    <head>
        <title>PHP Test</title>
    </head>
    <body>
        <h1><?php echo "Salom, PHP!"; ?></h1>
        <p>Hozirgi vaqt: <?php echo date('H:i:s'); ?></p>
    </body>
    </html>
```

## Muhim:

    Fayl nomi .php bilan tugashi kerak
    PHP kodi <?php bilan boshlanadi
    Har bir buyruq ; (nuqta-vergul) bilan tugaydi
    Izohlar uchun // yoki /* */ ishlatiladi

## 2.2. O'zgaruvchilar (Variables)
O'zgaruvchilar ma'lumotlarni saqlash uchun ishlatiladi. PHP da o'zgaruvchilar $ belgisi bilan boshlanadi.

## Sintaksis:

```
    $o'zgaruvchiNomi = qiymat;
```

# Misol:
```
    <?php
    $ism = "Aziz";
    $yosh = 25;
    $narx = 49.99;
    $aktiv = true;
    
    echo "Ism: $ism\n";
    echo "Yosh: $yosh\n";
    echo "Narx: $narx\n";
    echo "Aktiv: " . ($aktiv ? "Ha" : "Yo'q") . "\n";
```

# O'zgaruvchi nomlash qoidalari:

$ belgisi bilan boshlanadi
Harflar, raqamlar va _ (underscore) ishlatiladi
Raqam bilan boshlanmasligi kerak
Case-sensitive (katta-kichik harflar farqlanadi)

# To'g'ri:
```
$name
$user_name
$userName
$user1
$_temp
```
# Noto'g'ri:
```
$1user     // Raqam bilan boshlangan
$user-name // Defis ishlatilgan
$user name // Bo'shliq bor
```
# 2.3. Konstantalar (Constants)
Konstantalar o'zgarmas qiymatlarni saqlaydi. Ular bir marta belgilangandan keyin o'zgarmaydi.
# Usul 1: define() funksiyasi
```
<?php
define('SITE_NAME', 'Mening Saytim');
define('MAX_LOGIN_ATTEMPTS', 3);
define('PI', 3.14159);

echo SITE_NAME; // Mening Saytim
echo MAX_LOGIN_ATTEMPTS; // 3
```

# Usul 2: const kalit so'zi (PHP 5.3+)
```
<?php
const DB_HOST = 'localhost';
const DB_PORT = 3306;

class Config {
    const API_KEY = 'abc123xyz';
    public const TIMEOUT = 30; // PHP 7.1+
}

echo Config::API_KEY;
```
# Magic konstantalar:
```
<?php
echo __FILE__;      // Fayl yo'li
echo __DIR__;       // Direktoriya yo'li
echo __LINE__;      // Qator raqami
echo __FUNCTION__;  // Funksiya nomi
echo __CLASS__;     // Klass nomi
echo __METHOD__;    // Metod nomi
echo __NAMESPACE__; // Namespace
```

# 2.4. Ma'lumot turlari (Data Types)
PHP da 8 ta asosiy ma'lumot turi mavjud:

| Turi     | Ta'rif               | Misol         |
|----------|----------------------|---------------|
| String   | Matn                 | "Salom"       |
| Integer  | Butun son            | 42            |
| Float    | O'nli son            | 3.14          |
| Boolean  | True/False qiymat    | true / false  |
| Array    | To'plam (ro'yxat)    | [1, 2, 3]     |
| Object   | Obyekt               | new User()    |
| NULL     | Bo'sh qiymat         | null          |
| Resource | Tashqi manba/resurs  | fopen()       |

# String (Matn)
```
<?php
// Oddiy qo'shtirnoq - literal string
$name1 = 'Ali';
echo 'Salom, $name1'; // Salom, $name1

// Qo'sh qo'shtirnoq - interpolation
$name2 = 'Vali';
echo "Salom, $name2"; // Salom, Vali

// Heredoc sintaksis
$html = <<<HTML
<div class="user">
    <h1>$name2</h1>
    <p>Bu yerda HTML yozish qulay</p>
</div>
HTML;

// Nowdoc sintaksis (PHP 5.3+)
$code = <<<'CODE'
function test() {
    echo $variable; // Bu parse qilinmaydi
}
CODE;
```
# String funksiyalari:
```
<?php
$text = "  PHP Dasturlash  ";

// Uzunlik
echo strlen($text); // 19

// Bo'shliqlarni olib tashlash
echo trim($text); // "PHP Dasturlash"

// Katta harfga
echo strtoupper($text); // "  PHP DASTURLASH  "

// Kichik harfga
echo strtolower($text); // "  php dasturlash  "

// Qidirish
echo strpos($text, "PHP"); // 2

// Almashtirish
echo str_replace("PHP", "Python", $text);

// Bo'laklarga ajratish
$words = explode(" ", trim($text));
print_r($words); // ["PHP", "Dasturlash"]

// Birlashtirish
$joined = implode(", ", $words); // "PHP, Dasturlash"

// Substring
echo substr($text, 2, 3); // "PHP"

// PHP 8+: str_contains, str_starts_with, str_ends_with
echo str_contains($text, "PHP") ? "Mavjud" : "Yo'q";
echo str_starts_with($text, "  PHP") ? "Ha" : "Yo'q";
echo str_ends_with(trim($text), "lash") ? "Ha" : "Yo'q";
```

# Integer va Float
```
<?php
// Integer
$age = 25;
$temperature = -10;
$hex = 0xFF; // 255
$binary = 0b1010; // 10
$octal = 0755; // 493

// Float (Double)
$price = 99.99;
$pi = 3.14159;
$scientific = 1.5e3; // 1500

// Operatsiyalar
$sum = 10 + 5;      // 15
$diff = 10 - 5;     // 5
$product = 10 * 5;  // 50
$quotient = 10 / 5; // 2
$remainder = 10 % 3; // 1
$power = 2 ** 3;    // 8

// Matematik funksiyalar
echo abs(-10);      // 10
echo round(3.6);    // 4
echo ceil(3.1);     // 4
echo floor(3.9);    // 3
echo sqrt(16);      // 4
echo pow(2, 3);     // 8
echo max(1, 5, 3);  // 5
echo min(1, 5, 3);  // 1
echo rand(1, 100);  // Tasodifiy son

// Number formatting
$number = 1234567.89;
echo number_format($number, 2, '.', ','); // 1,234,567.89
```

# Boolean
