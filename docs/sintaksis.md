## 2. Asosiy Sintaksis
## PHP kodini yozishdan oldin, uning asosiy sintaksisini tushunish kerak. Bu bo'limda siz o'zgaruvchilar, ma'lumot turlari, operatorlar va asosiy funksiyalarni o'rganasiz.

## 2.1. PHP kodini yozish
## PHP kodi har doim <?php bilan boshlanadi va HTML ichida yoki alohida PHP faylida yozilishi mumkin.

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