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
``````
