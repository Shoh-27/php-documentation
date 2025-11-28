PHP 8+ — To'liq Professional Dasturlash Qo'llanmasi

Muallif so'zi
Ushbu qo'llanma PHP dasturlash tilini o'rganmoqchi bo'lgan har bir dasturchi uchun to'liq yo'riqnoma bo'lib xizmat qiladi. Kitob boshlang'ich darajadan tortib, professional va senior darajagacha bo'lgan barcha mavzularni qamrab oladi.
PHP — bu web dasturlashning eng mashhur tillaridan biri bo'lib, dunyodagi saytlarning 70% dan ortig'i PHP yordamida qurilgan. Laravel, Symfony, WordPress, Magento kabi mashhur platformalar PHP asosida ishlaydi.
Bu qo'llanmada siz nafaqat sintaksisni, balki real loyihalarda qo'llaniladigan ilg'or texnikalar, arxitektura patternlari, xavfsizlik tamoyillari va professional kodlash amaliyotlarini ham o'rganasiz.
Maqsad: Siz ushbu kitobni o'qib bo'lgach, professional PHP dasturchisiga aylanasiz va haqiqiy loyihalarni mustaqil ravishda boshqara olasiz.

Kirish
1.1. PHP nima?
PHP (Hypertext Preprocessor) — bu server tomonida ishlaydigan (server-side) skript dasturlash tili. PHP asosan dinamik web-saytlar va veb-ilovalar yaratish uchun ishlatiladi.
Asosiy xususiyatlari:

Open source va bepul
Barcha operatsion sistemalarda ishlaydi (Linux, Windows, macOS)
MySQL, PostgreSQL, MongoDB kabi ko'plab bazalar bilan integratsiya
Keng jamoat va dokumentatsiya
Laravel, Symfony kabi mashhur frameworklar

PHP qanday ishlaydi?
```
    [Foydalanuvchi] → [HTTP So'rov] → [Web Server] → [PHP Engine] → [Ma'lumotlar bazasi]
                                                        ↓
    [Foydalanuvchi] ← [HTML Javob] ← [Web Server] ← [PHP natija]
```

Foydalanuvchi brauzerda sayt ochganda, so'rov server-ga yuboriladi. Server PHP faylni ishga tushiradi, kerakli hisob-kitoblarni bajaradi, ma'lumotlar bazasidan ma'lumot oladi va natijani HTML formatida qaytaradi.

1.2. PHP ishlatiladigan sohalar
PHP juda keng qo'llaniladi va quyidagi sohalarda faol ishlatiladi:
1. Web saytlar va CMS tizimlar

WordPress (dunyodagi saytlarning 43%)
Joomla
Drupal

2. E-commerce platformalar

Magento
WooCommerce
OpenCart

3. Web ilovalar

Facebook (dastlab PHP da yozilgan)
Wikipedia
Slack
Mailchimp

4. REST API

Mobil ilovalar uchun backend
Microservice arxitekturalar
Uchinchi tomon integratsiyalar

5. CRM va ERP tizimlar

SugarCRM
VTiger CRM
Korxona ichki tizimlari

6. Data processing

CSV/Excel fayl qayta ishlash
Report generatsiya
Batch operatsiyalar


1.3. PHP 8.x dagi katta o'zgarishlar
PHP 8.0, 8.1, 8.2 va 8.3 versiyalarida juda ko'p yangi xususiyatlar qo'shildi. Bu o'zgarishlar tilni yanada samarali, xavfsiz va zamonaviy qildi.
PHP 8.0 (2020)
1. JIT Compiler (Just In Time)
Kod tezligini 2-3 baravar oshiradi
Matematik hisob-kitoblarda katta foyda.
2. Named Arguments
```
    function createUser($name, $email, $age = null) {
        // ...
    }
    
    // Eski usul
    createUser('Ali', 'ali@mail.com', 25);

    // Yangi usul (named arguments)
    createUser(
        email: 'ali@mail.com',
        name: 'Ali',
        age: 25
); 
```

3. Union Types
```
    function processValue(int|float $value): int|float {
        return $value * 2;
    }
```
4. Match Expression
```
    $result = match($status) {
        'pending' => 'Kutilmoqda',
        'approved' => 'Tasdiqlandi',
        'rejected' => 'Rad etildi',
        default => 'Noma\'lum'
    };
```
5. Nullsafe Operator
```
    // Eski usul
    $country = null;
    if ($user !== null) {
        if ($user->getAddress() !== null) {
            $country = $user->getAddress()->getCountry();
        }
    }

    // Yangi usul
    $country = $user?->getAddress()?->getCountry();
```
6. Constructor Property Promotion
```
    // Eski usul
    class User {
        public string $name;
        public string $email;
        
        public function __construct(string $name, string $email) {
            $this->name = $name;
            $this->email = $email;
        }
    }

    // Yangi usul
    class User {
        public function __construct(
            public string $name,
            public string $email
        ) {}
    }
```

PHP 8.1 (2021)
1. Enums
```
    enum Status {
        case Pending;
        case Approved;
        case Rejected;
    }
```
2. Readonly Properties
```
    class User {
        public function __construct(
            public readonly string $email
        ) {}
    }
```
3. Fibers (Async operatsiyalar)
```
    $fiber = new Fiber(function(): void {
        echo "Fiber boshlandi\n";
        Fiber::suspend();
        echo "Fiber davom etdi\n";
    });
```

PHP 8.2 (2022)
1. Readonly Classes
```
    readonly class Configuration {
        public function __construct(
            public string $host,
            public int $port
        ) {}
    }
```
2. Disjunctive Normal Form (DNF) Types
```
    function process((A&B)|C $input): (X&Y)|Z {
        // ...
    }
```

PHP 8.3 (2023)
1. Typed Class Constants
```
    class Status {
        public const string PENDING = 'pending';
        public const string APPROVED = 'approved';
    }
```
2. Dynamic Class Constant Fetch
```
    $constant = 'PENDING';
    echo Status::{$constant};
```

## PHP 8+ ning afzalliklari

| Xususiyat           | Ta'sir                       |
|---------------------|------------------------------|
| JIT Compiler        | 2–3x tezroq ishlash          |
| Union Types         | Xavfsizroq kod               |
| Match Expression    | Tozaroq sintaksis            |
| Nullsafe Operator   | Kamroq kod, ko'proq safety   |
| Enums               | Type-safe konstantalar        |
| Readonly Properties | Immutability                 |
| Attributes          | Clean metadata               |

## Xulosa
PHP — zamonaviy, tez va xavfsiz dasturlash tili. PHP 8+ versiyalari juda 
ko'p yangi xususiyatlar bilan keldi va bu til hozir boshqa zamonaviy tillar (Python, JavaScript) 
bilan raqobatlasha oladi. Ushbu qo'llanmada siz PHP ning barcha jihatlarini chuqur o'rganasiz va 
professional dasturchi bo'lib yetishasiz.
