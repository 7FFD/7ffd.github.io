---
layout: post
title:   "Зберіть свій ZX Spectrum"
categories:
    - ZX Spectrum
    - Harlequin 128
    - Beta Drive Interface
    - 256Kb modding
excerpt_separator: <!--more-->
---
Ви вже готові до вільного плавання і хочете "залізний" ZX Spectrum - є два варіанти - купити б/у (що може коштувати) або зібрати максимально сумісний ZX Spectrum на більш менш сучасній елементній базі.  
[Don Superfo](https://github.com/DonSuperfo/Superfo-Harlequin-128) зробив титанічну роботу, розвів схему ZX Spectrum 48k і 128k, щоб будь хто мав можливість відтворити ці легендарні комп'ютери. Але, трохи раніше, один британський хлопець Chris Smith захопився ідеєю відновити втрачені схеми ULA і йому це вдалося. Довгий і тернистий шлях по відновленню схеми був подоланий і відтворені з урахуванням більшості таймінгів, що робить цей клон ZX Spectrum максимально сумісним з оригінальним. Дуже рекомендую до читання книгу Кріса [The ZX Spectrum ULA: How to design a microcomputer](http://www.zxdesign.info/book/theZXSpectrumULA.shtml) 

![The ZX Spectrum ULA: How to design a microcomputer](/content/2024-08-10-Make-your-own-zx-spectrum/01-The ZX Spectrum ULA- How to design a microcomputer.jpg)

<!--more-->

На дворі бушує КОВІД, всі заперті вдома - час на домашні розваги! Я собі знайшов і досить цікаву :) Оскільки я люблю попаяти, замовив на якомусь маркет плейсі готову плату Harlequin 128 2D. Одночасно з тим, замовив у китаї всю розсипуху (ну щоб дешевше, потім частково пожалкував) і герконову клавіатуру!

![Зберіть свій ZX Spectrum, Герконова клавіатура](/content/2024-08-10-Make-your-own-zx-spectrum/02-reed-keyboard.jpeg "Зберіть свій ZX Spectrum, Герконова клавіатура")

Плати виглядали достатньо стильно

![Зберіть свій ZX Spectrum, Плата Harlequin 128 2D](/content/2024-08-10-Make-your-own-zx-spectrum/03-superfo-harlequin-128-plate.jpeg "Зберіть свій ZX Spectrum, Плата Harlequin 128 2D")

Крім мікросхем, замовив ще панельки для них, щоб не паяти безпосередньо на плату, бо різне може статися... Це не раз мене рятувало, бо випаювати мікросхеми ще те задоволення.  
Нажаль, в той час я не робив достатньо фото, тому передати процес і здоволення від запаювання і збирання всього до купи  - не можу :(
Так чи інакше, закінчивши цей цікавий процес, перейшов до підключення і наладки. Як кажуть, RTFM ніхто не відміняв, і відповідно комп з першого разу не завівся. Прийшлося погратися з джамперами, з дебільшого на ROM чіпі, щоб почав грузитися бейсік.
На початку замовив мікросхеми пам'яті ISSI HM628128ALP-10 але з 10 шт робочими виявилися тільки 2 і ті не довго протрималися. Може мені не підфортило, а може не треба було аж так сильно економити - не знаю. Факт залишається фактом, що треба перевіряти компоненти і купувати з перевірених джерел.

Зібраний Harlequin 128 2D
![Зберіть свій ZX Spectrum, Зібраний Harlequin 128 2D](/content/2024-08-10-Make-your-own-zx-spectrum/04-harlquin-128-2D-assembled.jpeg "Зберіть свій ZX Spectrum, Зібраний Harlequin 128 2D")

Тут вже використані хороші мікросхеми пам'яті, які працюють до сих пір.

Іншою проблемою виявилася кийтайська логіка, яка не розрахована на працю на граничних частотах. Справа в тому, що у цій версії Harlequin, генератор працює на частоті 28 мГц, а по даташитам, максимальна частота на який працюють лічильники 74HC138 має бути 30 мГц, але це не в випадку китайської логіки. Артефакти на екрані починалися після 2-3 хвилин запуску - зображення починало скакати і видно було, що є якісь проблеми з сінхронізацією.  
Довге гугління з різними експериментами не давали позитивного результату, поки я таки не прочитав до кінця мануал і не побачив маленьку примітку від автора, що краще для лічильників використати логіку фірми ST...
Замовивши і не економивши на постачальнику, купив оригінальну логіку... і проблема зникла. І таке буває...

З клавіатурою був свій окремий квест.

![Зберіть свій ZX Spectrum, Клавіатура в зборі](/content/2024-08-10-Make-your-own-zx-spectrum/05-reed-keyboard-assembled.jpeg "Зберіть свій ZX Spectrum, Клавіатура в зборі")

Не знаю з яких закромів "родіни" ці ділки з Одеси нарили комплекти для збору клавіатури, але вони потрапили в десятку.
Вона була як Лего без інструкції - всі процеси треба було видумувати самому - як підібрати висоту герконів, як відрегулювати висоту кріплення магнітів, як запаяти це все діло разом і щоб працювало... Не дивлячись на всі ці складності, клавіатура вийшла напрочуд удобною і легкою в користуванні. Навіть чутно як геркони клаціють, коли кнопки нажимаються - це окреме задоволення від користування нею. Говорю відповідально, як людина яка досить багато часу проводила за цією клавіатурою під час програмування на ассемблері.

Єдиним недоліком її є те, що це просто клавіатура, яка не призначеня для монтування плати спєка в середину. Це було реальне розчарування. При спробі розмістити плату в середені - не вистачало десь сантиметра. Але ж мій спєк і не повинен виглядати, як оригінальний (хоч і хотілося). 

Плату прикріпив на нижню кришку на стіїчки, а саму кришку поставив на стійки різної висоти, щоб добитися скосого профіля.
![Зберіть свій ZX Spectrum, Задня кришка клавіатури](/content/2024-08-10-Make-your-own-zx-spectrum/06-keyboard-backplate.jpeg "Зберіть свій ZX Spectrum, Задня кришка клавіатури")

З ліва на кришці прикручені роз'єми для джойстиків Sinclair 1/2, а з права Kempston і послідовний порт через AY.

![Зберіть свій ZX Spectrum, Верхня кришка клавіатури](/content/2024-08-10-Make-your-own-zx-spectrum/07-keyboard-top.jpeg "Зберіть свій ZX Spectrum, Верхня кришка клавіатури")

В зборі виглядає десь так:

![Зберіть свій ZX Spectrum, Зібраний Harlequin 128 2D в клавіатурі](/content/2024-08-10-Make-your-own-zx-spectrum/08-harlequin-inside-keyboard.jpeg "Зберіть свій ZX Spectrum, Зібраний Harlequin 128 2D в клавіатурі")

Наступним кроком, було підключення дисковода. Задля цього замовив у одного пана (до речі, пізніше ми знайшлися в одній ретро тусовці) на маркетплейсі плату з деталями для дискового контролера по типу Beta Drive. Однак, він був під роз'єм Орель-БК і під спєковський не пасував взагалі.
Прийшлося паяти перехідник, а з урахування що я ніколи не підключав такі девайси до спєка, то і результат видавася досить примарний.

Стоп, стоп, стоп... Тут я трохи поспішив. Насправді, ще до того як я вирішив зібрати контролер дисковода, задумувався, як щось підключити до спєка для комунікації через системний роз'єм.

![Зберіть свій ZX Spectrum, Експерименти з системним роз'ємом](/content/2024-08-10-Make-your-own-zx-spectrum/09-hw-port-0x77-0x75.jpg "Зберіть свій ZX Spectrum, Експерименти з системним роз'ємом")

Якщо по простому, ця схема являє собою дешифратор порту 0х77 і 0х79 і записує/читає байт в/з тригера. На макетці були додані світлодіоди для наглядності що плата працює:

![Зберіть свій ZX Spectrum, Макетна плата](/content/2024-08-10-Make-your-own-zx-spectrum/10-port-commumication.jpeg "Зберіть свій ZX Spectrum, Макетна плата")

Проста програма на бейсіку, яка записує в порт число:

![Зберіть свій ZX Spectrum, Програма запису на бейсіку](/content/2024-08-10-Make-your-own-zx-spectrum/11-port-communication-program.png "Зберіть свій ZX Spectrum, Програма запису на бейсіку")

Ну і сам результат запуску:

![Зберіть свій ZX Spectrum, Пуск програми](/content/2024-08-10-Make-your-own-zx-spectrum/12-port-communication-run.png "Зберіть свій ZX Spectrum, Пуск програми")

В той час я тільки починав розбиратися з різноманітними мікросхемами серії 74LS, тому тут були використані найпростіші логічні елементи і завдяки тому така проста схема вийшла досить громіздкою.

Але, як підтвердження концепції - цього було з головою! Як я радів, коли вона запрацювала, ці відчуття не передати.
Більш того, це додало впевненності і бажання двигатися далі.

Щож, повернемося до дискового інтерфейса. Після запаювання самої плати контролера і перехідника, настав час підключення.  

![Зберіть свій ZX Spectrum, Орель BDI з адаптером ZXBUS](/content/2024-08-10-Make-your-own-zx-spectrum/13-orel-bdi-with-adapter.jpeg "Зберіть свій ZX Spectrum, Орель BDI з адаптером ZXBUS")

І тут мене спіткали багато проблем одночасно:
1. ROM з комплекта контролера не підходив до Арлекіна, бо Орель має модифікований бейсік з своєю несумісною розкладкою клавіатури. Для вирішення питання, треба було переробити плату контролера для ROM 28c256 (вона розрахована на 27с256) і зашити TRDOS+BASIC48k.

2. Інший перекрут шлейфа дисковода для диску "А:". Для другого раз'єма необхідно перекрутити 10-й і 12-й провід, 
відносно 11-го (це відрізняється від стандартного кабеля для PC), таке підключення забезпечить роботу дисковода “A:”. Без цієї переробки дисковод “A:” розпізнаватися не буде!!!

3. Конфлікт з Kempston джойстик. Справа у тому, що контролер використовує порт 0x1F, так само як і джостик. Тому в усих спєках треба це враховувати і відключати джойстик, коли іде доступ до портів контролера. Це можна зробити по різному. В моєму випадку, я просто відключив джойстик повністю на стороні Арлекіна, але зробив його підключення на платі перехідника і відключав при активному сигналі BETA.

4. На ZXBUS Арлекіна не виведені +12В. Треба було обережно допаяти на пін роз'єма на платі спєка провід до +12В.

На пошук вирішення всих цих проблем у мене пішло доволі багато часу, десь з місяць до півтора.

Ще пізніше, модифікував схему контролера, щоб можна було відключати його автостарт в ТРДОС.

![Зберіть свій ZX Spectrum, Модифікації Орель BDI](/content/2024-08-10-Make-your-own-zx-spectrum/14-bdi-schematic-28c256-trd-autostart-on-off.jpeg "Зберіть свій ZX Spectrum, Модифікації Орель BDI")

Схема адаптера для контролера дисковода Орель-БК під ZXBUS:

![Зберіть свій ZX Spectrum, Адаптер для контролера дисковода Орель-БК під ZXBUS](/content/2024-08-10-Make-your-own-zx-spectrum/15-orel-bdi-adapter-zxbus-schematic.png "Зберіть свій ZX Spectrum, Адаптер для контролера дисковода Орель-БК під ZXBUS")

> При підключенні контролера через цей адаптер, ROM на контролері повинен бути вийнятий або відключений.

Ще декілька доробок було зроблено на платі контролера - це аварійне живлення по лінії +12В для К1818ВГ93. Справа в тому, що ця мікросхема потребує два живлення - +5В і +12В. Якщо пропадає одне з них, то є велика вірогідність пошкодити цю мікросхему. Тому існує багато способів забезпечити збережження її в неушкодженому стані (про роботу не йдеться). Один з них, це підключення +12В до +5В через діод, що забезпечить мікросхему від виходу з ладу, якщо не буде/пропаде +12В.

Крім того, в більшості клонів (в тому числі і Орелі), не особо заморочувалися з використанням сигналу ROMCS або постійно підключали його до +5В. Цей сигнал використовується для відключення стокового ROMу спєка, при підключенні зовнішніх девайсів. Я його використав по повній. На схемі адаптера є перемикач для вибора схеми роботи ROMа:
1. Повністю відключений, працює стоковий ROM компʼютера.

2. Буде активуватися тільки TRDOS ROM, бейсік буде працювати зі стокового ROMа.

3. Повне блокування стокового ROMа, бейсік буде працювати із ROMа на Адаптері.

На дисковод "А:" повісив емулятор, а на "В:" звичайний 3.5" дисковод. Єдиний момент, при використанні дискет, треба не забувати заклеювати віконце щільності запису, щоб дисковод думав, що там дискета на 720Кб.

![Зберіть свій ZX Spectrum, Дисководи](/content/2024-08-10-Make-your-own-zx-spectrum/16-disk-drives.jpeg "Зберіть свій ZX Spectrum, Дисководи")

Оскільки основним призначенням цього контролера було більш удобне і швидке збереження і читання файлів, це вивело на новий рівень удобство при програмуванні на асемблері.

Для ще більш продуктивної роботи, створив такий собі додаток до клавіатури, який дозволяв користуватися курсорними кноками без CapsShift, так само, як і іншими кнопками з верхнього ряду, призначені в редакторі асемблера для прокрутки сторінок, видалення символа DEL/BCKSP і інші зручності.

![Зберіть свій ZX Spectrum, Додаткова клавіатура](/content/2024-08-10-Make-your-own-zx-spectrum/17-cursor-keyboard.jpeg "Зберіть свій ZX Spectrum, Додаткова клавіатура")

Ця клавіатура повністю хардверна, тому в на програмному рівні нічого переробляти не треба було.

А так виглядає середа розкобки ALASM з повним "обвісом" мого спєка.

![Зберіть свій ZX Spectrum, Середа розробки ALASM](/content/2024-08-10-Make-your-own-zx-spectrum/18-alasm-at-work.jpeg "Зберіть свій ZX Spectrum, Середа розробки ALASM")

Я вже згадував, що все це робилося задля покращення користувацького досвіду і спрощення роботи в редакторі асемблера.
Як додаток до всього цього, було розширено пам'ять до 256Кб "малою кров'ю". На початку статті, я згадував про проблеми з пам'яттю і заміну на добротну RAM. З подивом дізнався, що у мене в спєку стоїть 256Кб але використовується тільки 128Кб.
Почав думати, як би використати інші 128Кб. На допомогу прийшов пентагон зі схемою розширення пам'яті аж до 4Мб. Ну аж так багато мені не потрібно, хотілося з мінімальніми змінами.
Була розроблена відповідна схема до переключення додаткових банок RAM разом зі сінхронізацією contended пам'яті, що використати інші 64Кб.

![Зберіть свій ZX Spectrum, Схема мода на 256Кб](/content/2024-08-10-Make-your-own-zx-spectrum/19-harlquin-mod-256Kb.png "Зберіть свій ZX Spectrum, Схема мода на 256Кб")

Збирання мода на прототипній платі

![Зберіть свій ZX Spectrum, Збирання мода на 256Кб](/content/2024-08-10-Make-your-own-zx-spectrum/20-256k-mod-assembling.jpeg "Зберіть свій ZX Spectrum, Збирання мода на 256Кб")

Підключення відповідних входів до точок на платі Арлекіна

![Зберіть свій ZX Spectrum, Підключення мода на 256Кб](/content/2024-08-10-Make-your-own-zx-spectrum/21-256k-mod-connecting1.jpeg "Підключення свій ZX Spectrum, Збирання мода на 256Кб")

Треба зауважити, що підключення А16 ніг мікросхем пам'яті потребувало відключення цих ніг від +5в/землі. Це треба було робити обережно, бо одна з них виконувала роль перехідного отвору, тому прийшлося робити обхід.

![Зберіть свій ZX Spectrum, Підключення мода на 256Кб](/content/2024-08-10-Make-your-own-zx-spectrum/22-256k-mod-connecting2.jpeg "Підключення свій ZX Spectrum, Збирання мода на 256Кб")

Виглядає не сильно привабливо але ж працює!

![Зберіть свій ZX Spectrum, Підключення мода на 256Кб](/content/2024-08-10-Make-your-own-zx-spectrum/23-256k-mod-connecting3.jpeg "Підключення свій ZX Spectrum, Збирання мода на 256Кб")

Перший пуск і ALASM детектить 256Кб пам'яті:

![Зберіть свій ZX Spectrum, Перший пуск мода на 256Кб](/content/2024-08-10-Make-your-own-zx-spectrum/25-256k-mod-done.jpeg "Підключення свій ZX Spectrum, Перший пуск мода на 256Кб")

Такий достатньо простий моддінг дав можливість використання більшого числа вікон вихідного коду в ALASM, що зменшило час компіляції і покращило ситуацію з підгрузкою кількох файлів в пам'ять при розробці.

В цій статті я згадав тільки про самі важливі модифікації при становленні моєї системи на основі клона ZX Spectrum.

А в наступних статтях я розповім - навіщо мені потрібна така потужна система...