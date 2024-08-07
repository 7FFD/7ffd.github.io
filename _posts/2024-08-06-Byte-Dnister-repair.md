---
layout: post
title:   "'Байт' Дністер, частина 2: Відновлення"
categories:
    - ZX Spectrum
    - Z80
excerpt_separator: <!--more-->
---
Що ж, порозглядали, полапали, прийшов час підключати...

!['Байт' Дністер, Перший запуск](/content/2024-08-06-Byte-Dnister-repair/IMG_7655.jpeg "'Байт' Дністер, Перший запуск")

І от халепа - не працює...
<!--more-->

Але з початку, зупинимося на особливостях підключення. Більшість клонів ZX Spectrum'а не мають звичних в наш час HDMI або навіть "тюльпанів". Тому в більшості їх приходилося підключати до радянських телевізорів напряму, бо ті теж не мали окремих входів, за кількома виключеннями.

Добре хоча б те, що інструкції по підключенню додавалися в документації до комп'ютера, з якої можна було зрозуміти, як краще це зробити. Як я згадував, зазвичай сигнали воводили прямо з ніжок мікросхем і мастер, який підключав, повинен був орієнтуватися що і як... Але, в цілях економії або ліні, або відсутності необхідних компоненів - підключали напряму. Це виливалося в спалені мікросхеми при скачках напруги або банального "прострілу" високої напруги з кінескопа.

На щастя, при вивченні документації і прозвоні ТВ роз'єма виявилося, що виходи буферизовані і мають відповідні резисторні ділільники для правильного підключення. Єдиний вивід S з Т34ВГ1 мав безпосереднє під'єднання до роз'єма, що було достатньо небезпечно. Ця мікросхема є найважливішою в цьому компі і спалити її було б дуже шкода.

Озброївшись документацією, тестером і DIN роз'ємом пішов паяти перехідник на SCART.

!['Байт' Дністер, Перехідник на SCART](/content/2024-08-06-Byte-Dnister-repair/IMG_7665.jpeg "'Байт' Дністер, Перехідник на SCART")

Оті 2 проводки зі SCART'а, підключені через резистори до затискача-пробніка, потрібні щоб SCART перейшов у режим RGB. Підключається до +5В, я його буду чіпляти до плюсової ножки живлення будь якої мікросхеми.

3..2..1 Пуск!

!['Байт' Дністер, Перший запуск](/content/2024-08-06-Byte-Dnister-repair/IMG_7655.jpeg "'Байт' Дністер, Перший запуск")

... і ось така картина, на кнопки не реагує, на ресет - іноді змінюється щось на екрані. Ну, ок, принаймні є зображення, а це означає що "чіпсет" Т34ВГ1 живий 100%. Процесор з великою вірогідністю теж, бо був би "матрац". Таким чином зменшуємо коло підозрюваних до ROM чіпа і пам'яті.

Випаювати ROM мені було лінь, та і збоку був не розпаяний 28 піновий роз'єм, на який я вирішив запаяти площадку під чип з ROM'ом. Після цього перекинути вибір чіпа на площадку, а той ROM відключити. Так і зробив.

!['Байт' Дністер, Переключення ROM](/content/2024-08-06-Byte-Dnister-repair/IMG_7657.jpeg "'Байт' Дністер, Переключення ROM")

Записавши в 28с256 тест для пам'яті Test48 і вставивши в площадку, компік подав деякі признаки життя.

!['Байт' Дністер, Тест пам'яті](/content/2024-08-06-Byte-Dnister-repair/IMG_7659.jpeg "'Байт' Дністер, Тест пам'яті")

Тест показав, що 8й біт практично взагалі не працює... Це говорило про те, що мікросхема пам'яті на лінії D7 була бракована. Добре, випаюємо, ставимо площадку і... мандруємо шукати в інтернеті КР565РУ5. Знайшов достатньо швидко і одразу замовив. 

Поки чекав на посилку, випаяв рідний ROM і зробив дамп. В середині був звичайний бейсік від спектрума зі зміненим роком в привітанні.

За добу забрав замовлені мікросхеми і одразу ж поставив для перевірки.

Перемога! Запустилося!

!['Байт' Дністер, Тест пам'яті, заход №2](/content/2024-08-06-Byte-Dnister-repair/IMG_7662.jpeg "'Байт' Дністер, Тест пам'яті, заход №2")

Але не довго я насолоджувався. Треба було одразу запустити тест пам'яті, а не ставити бейсік в змінний ROM.

!['Байт' Дністер, Тест пам'яті, заход №3](/content/2024-08-06-Byte-Dnister-repair/IMG_7663.jpeg "'Байт' Дністер, Тест пам'яті, заход №3")

Щоб напевно, вирішив ще спробувати перевірити DiagROM'ом - діагноз підтвердився.

!['Байт' Дністер, Тест пам'яті, DiagROM](/content/2024-08-06-Byte-Dnister-repair/IMG_7666.jpeg "'Байт' Дністер, Тест пам'яті, DiagROM")

Нажаль, мікросхема на 3му біті була теж не справна, тільки на далеких адресах. Але ж я запасливий і купив не одну РУшку :)

Випаюю, ставлю площадку і нову мікросхему. Тепер все в порядку і працює, як треба.

!['Байт' Дністер, Тест пам'яті, DiagROM фінал](/content/2024-08-06-Byte-Dnister-repair/IMG_7671.jpeg "'Байт' Дністер, Тест пам'яті, DiagROM фінал")

Супер, далі проганяю стандартні тести DiagROM'а. Все наче нормально.

Підключивши перехідник для магнітофона, пробую загрузити першу програму з плівки. Для цього ставлю ROM з бейсіком.

!['Байт' Дністер, Бейсік](/content/2024-08-06-Byte-Dnister-repair/IMG_7679.jpeg "'Байт' Дністер, Бейсік")

Теж хіба працює...

!['Байт' Дністер, Загрузка з плівки](/content/2024-08-06-Byte-Dnister-repair/IMG_7681.jpeg "'Байт' Дністер, Загрузка з плівки")

Таки працює!

!['Байт' Дністер, Вдала загрузка з плівки ](/content/2024-08-06-Byte-Dnister-repair/IMG_7682.jpeg "'Байт' Дністер, Вдала загрузка з плівки")

На завершення, хотів би додати, що конкретно цей екземпляр, був бракований ще з завода. Пломба була на місці, якось зіпсувати мікросхеми пам'яті, не відкриваючи його і не пошкодивши інші компоненти, мені здається - практично не можливо.

Мабуть за рахунок цього, він зберігся в достатньо ідеальному стані.

Далі буде розширення його можливостей: підключення системного роз'єма і спроба поприятилювати з Beta drive'ом.

Не перемикайтеся, буде цікаво!