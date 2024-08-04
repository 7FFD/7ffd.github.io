---
layout: post
title:   "'Байт' Дністер, частина 1: Початок"
categories:
    - ZX Spectrum
    - Z80
excerpt_separator: <!--more-->
---
![Байт Дністер, м. Бендери](/content/2024-08-02-Byte-Dnister-inception/IMG_7686.JPG "Байт Дністер, м. Бендери")

Колись, в давні часи, років 30 тому, батьки купили мені щось подібне на компʼютер - називалося воно: приставка телевізійна програмована, а по простому - Байт. Це був мій перший комп'ютер, який визначив моє майбутнє і затягнув мене у вир програмування і ІТ, ще за довго до того, як це стало трендом.

<!--more-->

Ще в 2019 мене накрила ностальгія і я вирішив знайти компʼютер з якого все почалося. Це виявилося не простою справою, оскільки, як виявилося, клонів ZX Spectrum на пост радянському просторі була сила силенна.
Пополювавши кілька місяців на OLX, так і не знайшов чого шукав. Прийшлося вибирати з того що було - першою знахідкою був Олімпік-С... але, то інша історія. Після вивчення "мат частини" виявилося, що існує цілий всесвіт, який пов'язаний з ZX Spectrum клонами. Тоді я відкрив для себе Harlequin 128. На щастя, на якомусь маркетплейсі, знайшов плати + замовив у китаї всі необхідні компоненти і вирішив зібрати свій перший (а може вже дургий) спектрум. Ну, як кажу, то був початок.

НАРЕШТІ, дякуючи одному знайомому з ретро-спільноти (Іван @Ivan_MadKiller, привіт :), таки вполював свій перший комп.
Це було дововижно, не за всі гроші світу і в досить гарній комплектації. Це був ВІН - Байт... той самий, червоненький, дуже схожий на оригіналний ZX Spectrum, але то не важливо. Продавець узгодив покупку і за добу я забрав його на Новій Пошті. Мабуть таких відчуттів я не відчував навіть тоді, коли мені принесли той, самий перший. Розпакувавши і перевіривши комплектацію, я був здивований, що сам комп'ютер був в дуже гарному стані - я пам'ятаю свій старий - він був з практично стертими кнопками і з дійсно видимими слідами уживання. Пізніше розповім, чому він так добре зберігся.

![Байт Дністер, вид ззаду](/content/2024-08-02-Byte-Dnister-inception/IMG_7687.JPG "Байт Дністер, вид ззаду")

Пломба була на місці... і судячи з матеріала, таки була орігінальна. Зазвичай, використовували звичайний пластилін, але тут була та сама тягуча маса, яку дуже важко виковиряти і зняти з захисного гвинтика.

![Байт Дністер, вид ззаду](/content/2024-08-02-Byte-Dnister-inception/IMG_7688.JPG "Байт Дністер, вид ззаду")

Ще й можна розгледіти напис - ОТК.

![Байт Дністер, вид ззовні](/content/2024-08-02-Byte-Dnister-inception/IMG_7689.JPG "Байт Дністер, вид ззовні")
 
Нічого надзвичайного: ROM, процесор, "чіпсет" (або подоба ULA, не копія!), 8 мікросхем пам'яті РУ5 і розсипуха, на якій побудований буфер джойстіка з буферами відео вихода.

![Байт Дністер, клавіатура](/content/2024-08-02-Byte-Dnister-inception/IMG_7690.JPG "Байт Дністер, клавіатура")
 
 Клавіатура має досить цікавий дізайн, не герконова, а проста пружинна з контактними площадками. Спектрум був достатньо дешевим компопм, тому дизайн софта включав програмний "debounce" кнопок, що спрощувало конструкцію клавіатури.

![Байт Дністер, клавіатура](/content/2024-08-02-Byte-Dnister-inception/IMG_7691.JPG "Байт Дністер, клавіатура")

Окремо зупинюся на клавіатурі і розповім мою теорію, чому комп не був у використанні, що пізніше підтвердилося діагностикою. Особливістю цієї клавіатури є те, що наклейки виконані з матеріалу, який дуже нагадує пофабований пластир.
Пам'ятаю, на моєму Байті, клавіатура дуже швидко стерлася, оскільки пальці потіють і за деякий час фарба з наклейок починає стиратися. Ця клавіатура виглядає незайманною.

![Байт Дністер, блок живлення низ](/content/2024-08-02-Byte-Dnister-inception/IMG_7692.JPG "Байт Дністер, блок живлення низ")

Блок живлення виглядав дещо дивно, у мене був інший і важчий. Як виявилося, цей блок живлення імпульсний, а у мене був звичайний трансформатор з діодним мостом і КРЕН5 в середені. 

У цього екземпляра навіть попередження написано на пузі - не вмикати без навантаження. Тому, щоб не зіпсувати, вирішив підключити одноватний резистор на 50 Ом, щоб емулювати навантаження. На диво, блок живлення запрацював і видав ~5В постійного струму.

![Байт Дністер, блок живлення індикація](/content/2024-08-02-Byte-Dnister-inception/IMG_7693.JPG "Байт Дністер, блок живлення індикація")

![Байт Дністер, блок живлення верх](/content/2024-08-02-Byte-Dnister-inception/IMG_7694.JPG "Байт Дністер, блок живлення верх")

![Байт Дністер, блок живлення в середині](/content/2024-08-02-Byte-Dnister-inception/IMG_7695.JPG "Байт Дністер, блок живленняв середині")

Окрім цього, в комплекті були касета, книжечки і джойстік.

![Байт Дністер, книжечки](/content/2024-08-02-Byte-Dnister-inception/IMG_7698.JPG "Байт Дністер, книжечки")

Одна з технічними даними і інструкцією підключення до телевізорів.

![Байт Дністер, книжечка підключення](/content/2024-08-02-Byte-Dnister-inception/IMG_7700.JPG "Байт Дністер, книжечка підключення")

Інша з вступною інформацією по програмуванню, бейсіку і іншим можливостям.

![Байт Дністер, книжечка використання](/content/2024-08-02-Byte-Dnister-inception/IMG_7699.JPG "Байт Дністер, книжечка використання")

Продавець докинув якийсь ноу-нейм джойстік, де навіть роз'єм не співпадав з Байтовським. Тим не менш, джойстік зроблений досить якісно і з цікавим конструкторськиім рішенням.

![Байт Дністер, джойстик](/content/2024-08-02-Byte-Dnister-inception/IMG_7696.JPG "Байт Дністер, джойстик")

Мікроперемикачі право-ліво - закріплені в площені так, щоб при качанні в право-ліво, перемикачі втискалисяв в дно джойстика.

![Байт Дністер, джойстик в розібраному стані](/content/2024-08-02-Byte-Dnister-inception/IMG_7701.JPG "Байт Дністер, кджойстик в розібраному стані")

А вверх-вниз натискання відбувалося штоком, який мав ступінь свободи в болчку, на якому закріплені мікроперемикачі, яких не видно на фото.

![Байт Дністер, джойстик в розібраному стані](/content/2024-08-02-Byte-Dnister-inception/IMG_7702.JPG "Байт Дністер, джойстик в розібраному стані")

Важкий і дость удобний у використанні. Спробував його в іграх - змішанні відчуття, але досвід цікавий.

В наступному пості розповім про спробу його підключення і виправлення несправностей...

Далі буде!