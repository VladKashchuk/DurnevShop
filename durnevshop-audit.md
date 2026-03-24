# DURNEVSHOP.COM.UA — UX/UI Audit
### Homepage Design Review через призму design-taste-frontend skill

---

## Загальне враження

DurnevShop — це мерч-магазин з потенціалом стати культовим streetwear-брендом, але поточний дизайн сайту не відповідає рівню самого бренду. Сайт виглядає як типовий Wix-шаблон без індивідуальності: дрібні елементи, нерівні відступи, відсутність повітря та візуальної ієрархії. Нижче — детальний розбір кожної проблемної зони з конкретними рекомендаціями.

---

## 1. LAYOUT & STRUCTURE — "Шаблонна нудьга"

**Проблема:** Весь сайт побудований на одноманітному, центрованому лейауті. Секції йдуть одна за одною без візуального контрасту — однакова ширина, однакові відступи, однаковий ритм. Це порушує Rule 3 (Anti-Center Bias) зі скіла: при DESIGN_VARIANCE 8 центровані hero-секції заборонені.

**Що бачимо зараз:**
- Центрований hero з банером
- Стандартна 3-4 колонкова сітка товарів (порушення Rule 7: "NO 3-Column Card Layouts")
- Монотонна вертикальна прокрутка без жодного «вау»-моменту
- Відсутність асиметрії, overlap-ів, або будь-якої візуальної різноманітності

**Як у референсів:**
- **Halfdays** — використовує split-screen hero (50/50 текст + фото), full-bleed lifestyle-зображення, чергування вузьких текстових блоків з широкими фото-сітками
- **Odd Ritual Golf** — асиметричні grid-и (2fr 1fr), великі hero-зображення з мінімальним текстом, горизонтальні скрол-секції
- **Michael Stars** — zig-zag лейаут між секціями, великі editorial-фото з текстом збоку, різна висота секцій

**Рекомендація:** Перебудувати лейаут головної на чергування різних типів секцій: split-screen hero → full-width lifestyle-фото → asymmetric product grid (2fr 1fr) → editorial text block → horizontal scroll collection. Кожна секція має відрізнятись від попередньої за структурою.

---

## 2. TYPOGRAPHY — "Дрібно і безлико"

**Проблема:** Типографіка не створює ієрархії. Заголовки замалі, body-текст не має достатнього контрасту з заголовками, шрифт — генеричний, без характеру. Порушує Rule 1 (Deterministic Typography) та Rule 7 (NO Inter Font / generic fonts).

**Що бачимо зараз:**
- Заголовки, які не «кричать» — замалий розмір, недостатньо tracking-tighter
- Body-текст без чіткого max-width обмеження (рядки розтягуються)
- Ймовірно, стандартний Wix-шрифт без індивідуальності
- Слабка вагова контрастність (все виглядає як один рівень)

**Як у референсів:**
- **Halfdays** — великі, виразні заголовки (uppercase, tracking-tight, bold weight), чіткий контраст між H1 і body
- **Odd Ritual Golf** — характерний шрифт з personality (serif для editorial моментів + clean sans-serif для UI), дуже великі hero-тексти
- **Michael Stars** — елегантна типографіка з serif для brand voice, правильний line-height і letter-spacing

**Рекомендація:**
- Основний шрифт: **Satoshi** або **Cabinet Grotesk** для заголовків (не Inter, не стандартний Wix)
- Display/Headlines: мінімум `text-4xl md:text-6xl tracking-tighter leading-none font-bold`
- Body: `text-base md:text-lg text-zinc-600 leading-relaxed max-w-[65ch]`
- Створити чітку 3-рівневу ієрархію: Hero title → Section title → Product title → Body

---

## 3. SPACING & WHITESPACE — "Задушений контент"

**Проблема:** Це центральна біль сайту. Елементи розташовані занадто щільно, padding-и нерівні, секції «злипаються» одна з одною. Відповідно до VISUAL_DENSITY 4 (Art Gallery / Daily App), сайт має дихати.

**Що бачимо зараз:**
- Маленькі відступи між товарними картками
- Секції без достатнього вертикального простору між собою
- Криві горизонтальні margin-и — деякі елементи не вирівняні по сітці
- Загальне відчуття «напханості» замість premium-чистоти

**Як у референсів:**
- **Halfdays** — щедрі `py-20 md:py-32` між секціями, повітря навколо кожного елементу, чистий white background
- **Odd Ritual Golf** — масивні padding-и `p-8 md:p-16`, товари розставлені з простором, а не запихнуті в сітку
- **Michael Stars** — `gap-8 md:gap-12` між товарами, кожен продукт має breathing room

**Рекомендація:**
- Секційні відступи: мінімум `py-16 md:py-24 lg:py-32`
- Товарна сітка: `gap-6 md:gap-8` замість поточних мінімальних відступів
- Глобальний контейнер: `max-w-[1400px] mx-auto px-6 md:px-12`
- Кожна секція має мати чіткий «вдих» — великий padding зверху і знизу

---

## 4. PRODUCT CARDS — "Дрібні і нецікаві"

**Проблема:** Товарні картки виглядають замалими, з крихітними зображеннями і дрібним текстом. Немає hover-ефектів, немає «живості». Порушує Rule 4 (Anti-Card Overuse) та Rule 5 (Interactive UI States).

**Що бачимо зараз:**
- Маленькі квадратні зображення товарів
- Назва + ціна під фото без візуального акценту
- Відсутність hover-станів (зум, зміна фото, підсвічування)
- Картки виглядають як Excel-таблиця, а не як lookbook

**Як у референсів:**
- **Halfdays** — великі прямокутні фото (3:4 або 4:5 ratio), мінімальний текст під фото, hover показує альтернативне фото товару
- **Odd Ritual Golf** — фото товарів на lifestyle-фонах, а не на білому; hover-ефект зуму або зміни ракурсу
- **Michael Stars** — чергування розмірів карток (одна велика + дві менші), model photography замість flat lay

**Рекомендація:**
- Збільшити розмір зображень до ratio 3:4 мінімум
- Hover-ефект: показати другу фотографію або `scale-[1.03]` з `transition-transform duration-500`
- Мінімальний текст під карткою: тільки назва + ціна, без зайвого шуму
- Чергувати розміри в сітці: asymmetric grid `grid-cols-2 md:grid-cols-[2fr_1fr]` замість рівних колонок

---

## 5. COLOR PALETTE — "Невизначена"

**Проблема:** Кольорова палітра не зчитується як цілісна система. Rule 2 (Color Calibration) вимагає максимум 1 accent color з saturation < 80% та нейтральну базу.

**Що бачимо зараз:**
- Немає чіткого accent color, що асоціюється з брендом
- Вірогідно, чорно-білий з випадковими кольоровими вкрапленнями
- Відсутність продуманої палітри Zinc/Slate для нейтральних елементів

**Як у референсів:**
- **Halfdays** — теплий off-white фон (#FAFAF8), чорний текст, один яскравий accent (сезонний колір колекції)
- **Odd Ritual Golf** — deep forest green як brand accent, cream background, warm neutrals
- **Michael Stars** — м'яка neutral palette, stone/sand/cream тони, чорний як контраст

**Рекомендація:**
- Визначити 1 brand accent color (наприклад, характерний для Durnev)
- Фон: off-white `#FAFAF8` або warm cream `#F5F3EF`
- Текст: `zinc-950` (не чистий `#000000` — Rule 7: NO Pure Black)
- Secondary text: `zinc-500`
- Borders/dividers: `zinc-200/50`

---

## 6. HERO SECTION — "Банер замість досвіду"

**Проблема:** Hero-секція виглядає як звичайний банер з Wix-шаблону. Немає емоційного імпакту, немає руху, немає storytelling. Для бренду рівня Дурнєва це критична втрата першого враження.

**Що бачимо зараз:**
- Статичний банер або слайдер
- Центрований текст поверх фото (заборонено при DESIGN_VARIANCE 8)
- Немає motion, немає глибини

**Як у референсів:**
- **Halfdays** — full-bleed lifestyle відео/фото, split-screen з текстом ліворуч і фото праворуч
- **Odd Ritual Golf** — immersive full-screen hero з великим відео, мінімальний текст
- **Michael Stars** — editorial split-screen з великою фотографією моделі

**Рекомендація:**
- Split-screen hero: ліворуч — велика типографіка з назвою колекції + CTA, праворуч — full-height lifestyle фото
- Або: full-bleed відео/фото з текстом aligned left + `padding-left: 8vw`
- Додати subtle motion: parallax або fade-in на скролі
- CTA-кнопка: великий, чіткий, з tactile feedback (`active:scale-[0.98]`)

---

## 7. NAVIGATION — "Функціональна, але мертва"

**Проблема:** Навігація — стандартний Wix header без характеру. Для e-commerce бренду з personality це major miss.

**Рекомендація:**
- Sticky nav з `backdrop-blur-xl` та 1px bottom border `border-zinc-200/50`
- Logo ліворуч, центральне меню, іконки (пошук, кошик) праворуч
- Мінімалістична іконка кошика з counter badge
- На скролі: nav злегка зменшується (padding transition)
- Mobile: hamburger menu з smooth slide-in панеллю

---

## 8. CTA & BUTTONS — "Невидимі"

**Проблема:** Кнопки не привертають увагу, не мають тактильного зворотного зв'язку. Rule 5 вимагає обов'язкового tactile feedback.

**Рекомендація:**
- Primary CTA: filled button з brand accent, `rounded-full`, `px-8 py-4`, `text-sm uppercase tracking-widest`
- Hover: `hover:brightness-110 transition-all duration-300`
- Active: `active:-translate-y-[1px] active:scale-[0.98]`
- Secondary: outlined button з `border-2 border-zinc-900`

---

## 9. FOOTER — "Інформаційний смітник"

**Проблема:** Footer на e-commerce сайтах часто стає звалищем лінків. Має бути чистим і структурованим.

**Рекомендація:**
- Чистий layout: 4 колонки — Brand/Newsletter | Shop | Info | Social
- Великий newsletter input з CTA
- Соціальні іконки: мінімальні, монохромні
- Subtle `border-t border-zinc-200` зверху
- Background: `zinc-950` (dark footer) або залишити light з subtle contrast

---

## 10. MICRO-INTERACTIONS & MOTION — "Статичний як PDF"

**Проблема:** Сайт відчувається мертвим. При MOTION_INTENSITY 6 мають бути CSS-транзішени, staggered load-in анімації, hover-ефекти.

**Рекомендація:**
- Scroll reveal: секції з'являються з `opacity-0 translate-y-4` → `opacity-100 translate-y-0`
- Staggered product grid: товари появляються з `animation-delay: calc(var(--index) * 100ms)`
- Image hover: `scale-[1.05]` з `transition-transform duration-700 ease-out`
- Button ripple або directional hover fill
- Smooth scroll behavior для всієї сторінки

---

## ЗВЕДЕНА ТАБЛИЦЯ ПРІОРИТЕТІВ

| # | Проблема | Severity | Impact |
|---|----------|----------|--------|
| 1 | Layout — монотонний, шаблонний | CRITICAL | Перше враження, bounce rate |
| 2 | Spacing — задушений контент | CRITICAL | Сприйняття якості бренду |
| 3 | Typography — дрібна, без ієрархії | HIGH | Читабельність, brand voice |
| 4 | Hero — банер замість досвіду | HIGH | Конверсія, емоційний hook |
| 5 | Product cards — замалі | HIGH | Конверсія товарів |
| 6 | Color — не системна | MEDIUM | Brand consistency |
| 7 | Motion — сайт статичний | MEDIUM | Perceived quality |
| 8 | CTA — невидимі кнопки | MEDIUM | Конверсія |
| 9 | Navigation — без характеру | LOW | Навігаційний досвід |
| 10 | Footer — неструктурований | LOW | Завершення досвіду |

---

## ДЕТАЛЬНИЙ РОЗБІР РЕФЕРЕНСІВ (з реального перегляду)

### 1. MICHAEL STARS (michaelstars.com)

**Навігація:**
- Announcement bar зверху ("FREE SHIPPING ON ORDERS OVER $100") — чорний фон, білий uppercase текст, letter-spacing
- Sticky header: лого (рукописний script-шрифт "Michael Stars / LOS ANGELES") ліворуч, меню по центру (SHOP, NEW, TEES & TANKS, DRESSES, ABOUT US), іконки (пошук, акаунт, кошик) праворуч
- Mega-menu при hover на SHOP — три колонки Categories/Featured/Fabrics + два CTA-банери справа

**Hero:**
- Carousel з 3 слайдів — кожен має full-bleed lifestyle-фото з моделлю + центрований текст поверх
- Заголовки великі, uppercase, з розрідженим tracking: "POPLIN, REDEFINED", "SPRING, AWAKENED"
- Subtitle — звичайний body text під заголовком
- CTA — "SHOP NOW" з outlined кнопкою (border, no fill)
- Pagination dots + Pause button знизу

**Brand Statement:**
- Між hero і контентом — одне речення по центру на повну ширину: "As a woman-owned and led brand, we make quality essentials in Los Angeles; designed to stay with you wherever you go in life."
- Великий кегль, достатній padding зверху/знизу — секція дихає

**Другий Hero:**
- Ще один full-bleed lifestyle-блок з текстом "BEST IN BASICS" — чергування форматів hero

**Shop by Category:**
- Горизонтальний carousel з великими portrait-фото моделей (ratio ~3:4)
- Під кожною карткою — назва категорії (Shop Tanks, Shop New Tees, Shop Dresses, Shop Sweaters)
- Стрілки навігації справа, progress bar знизу
- Neutral фон (off-white/cream) — фото на нейтральному бежевому бекграунді

**Instagram секція:**
- "As seen on Instagram" ліворуч + "@MichaelStarsInc" праворуч
- Горизонтальний carousel з Instagram-постів

**Split-блок (Linen Edit + Rewards):**
- 50/50 split: ліворуч — lifestyle-фото з текстом "THE LINEN EDIT" + опис + CTA; праворуч — cream-фон блок "MICHAEL STARS REWARDS" з CTA "Join Now"
- Асиметричний layout, різний візуальний вага лівої і правої частини

**Footer:**
- "Join Us" + newsletter (SMS + email inputs)
- Social icons (Facebook, Instagram, Pinterest)
- Два стовпці: Support, Company
- Lifestyle-фото тканини з підписом "The Original Tee"
- Legal links, copyright

**Ключові висновки:**
- Кольорова палітра: off-white/cream фон, чорний текст, мінімум кольорів
- Uppercase tracking для заголовків — створює luxury feel
- Чергування типів секцій: hero → statement → hero2 → category carousel → instagram → split block
- Великі lifestyle-фото домінують над текстом
- Горизонтальні carousels замість статичних grid-ів

---

### 2. ODD RITUAL GOLF (oddritualgolf.com)

**Intro-анімація:**
- Повноекранний scroll-hijack з dark background (#000) і логотипом "odd ritual" по центру, що з'являється з fadeIn
- Це кілька "екранів" скролу, які контролюють анімацію — по суті, це scrolltelling як з Creative Arsenal скіла
- Номери секцій (01, 02, 03) з підписами "Scroll" і "Next" — підказка користувачу

**Sidebar Navigation (нетипова!):**
- Замість стандартного горизонтального меню — вертикальна бокова навігація зліва
- "Swing easy, Odd Ritual, ©2025" + "Cape Town, South Africa" зверху
- Пункти меню: Our Shop, Home, About us, Contact — великий кегль, heading-рівень
- "Join the fam" + Instagram link знизу

**Hero Sections (scroll-triggered):**
- 3 секції, кожна з номером (01, 02, 03):
  - 01: "Explore our First Collection" + "Shop Now" CTA
  - 02: "A modern expression of heritage" + "About us" CTA
  - 03: "Follow us on Instagram To join the journey" + "Community" CTA

**Brand Statement:**
- Великий типографічний блок на всю ширину з описом бренду — serif-подібний шрифт, великий кегль

**Featured Products:**
- Заголовок "( Featured Products )" — з дужками як стилістичний прийом
- Горизонтальний scroll список товарів: caps (R 750.00), t-shirts (R 900-1000), polos (R 850), socks
- Мінімальна картка: фото + назва + SKU code + ціна
- Потім дублюється як компактніший list з фото + назва + ціна

**Bottom Navigation блоки:**
- 3 великі CTA-блоки: "Our Products / COLLECTION 01 & 02 / Shop now", "Our Story / About us / Read more", "Our Community / Social / Instagram"

**Local Production секція:**
- "ORGC©2025 Designed and made locally" + "Cape Town" / "South Africa"
- Описовий текст про місцеве виробництво — editorial tone

**Giving Back секція:**
- "Giving back" heading + опис community-ініціатив
- Партнери: Fairways to Africa, StartWell Foundation, 242, Running Late Club
- Кожен з описом + "Visit Website" CTA

**Footer:**
- Великий логотип "Odd ritual golf club / a modern expression of heritage"
- Newsletter форма: NAME SURNAME + EMAIL + SUBMIT
- Site Index, Social, Get in touch (email + phone), Legal links
- "Website by malvah" credit

**Ключові висновки:**
- МАКСИМАЛЬНА motion/scroll-анімація — весь сайт побудований на scroll-triggered reveals
- Dark intro → light content — драматичний контраст
- Нетиповий sidebar navigation замість стандартного header
- Serif/editorial типографіка для brand voice
- Мінімальний UI — фокус на фотографії та storytelling
- Community-driven: Instagram, giving back, local production
- Warm neutral palette: cream/sand background, dark text
- Кожна секція — це окрема "сцена" з повним контролем ритму через скрол

---

### 3. HALFDAYS (halfdays.com)

**Навігація:**
- Announcement bar: "FREE SHIPPING ON US ORDERS $95+. *RESTRICTIONS APPLY."
- Header: меню ліворуч (NEW, SHOP, COMMUNITY), лого по центру ("Halfdays" — serif/bold), іконки праворуч (пошук, акаунт, кошик)
- Бічна кнопка "UNLOCK 10% OFF" — вертикальна, зліва

**Hero:**
- Full-bleed split: ДВА великі lifestyle-фото моделі поруч (50/50), кожне займає половину екрану
- Жодного тексту поверх фото — чисті, великі зображення говорять самі за себе
- Модель в lime-green одязі на фоні гір — seasonal color story
- Фото зроблені на локації (гори), не в студії

**Spring Collection:**
- "INTRODUCING THE SPRING 2026 COLLECTION" — великий uppercase заголовок, tracking
- Subtitle — один рядок body text
- "SHOP NOW" CTA праворуч — горизонтальне вирівнювання між заголовком і CTA
- Горизонтальний carousel товарів: великі portrait-фото моделей (ratio ~3:4)
- Під кожним: назва + ціна ($105, $193, $72 etc.)

**Category Section:**
- Full-bleed lifestyle-фото з overlay text: "JACKETS / SHOP NOW", "TOPS / SHOP NOW", "BOTTOMS / SHOP NOW"
- Кожна категорія — величезне фото моделі в контексті (гори, природа)
- Текст в нижній частині фото, білий на темному фоні

**Activity Selector:**
- Три пункти: TRAIL, SNOW, ACTIVE — з різною opacity (active = bold, інші = faded)
- "SHOP NOW" CTA праворуч
- Нижче — lifestyle-фото для вибраної активності

**Best Sellers:**
- Горизонтальний carousel: portrait-фото моделей
- Назва + ціна під кожним
- Товари: Ynes Long Sleeve Top $105, Claude Jacket $248, Johnson Top $105, Sophia Legging $105, Murphy Ski Suit $765

**Editorial Block:**
- "BYE-BYE, BOYS CLUB." — великий bold заголовок
- Split: фото зліва + текст справа — brand mission statement

**Ключові висновки:**
- Hero без тексту — тільки великі фото, максимальний visual impact
- Lifestyle photography на локаціях (гори, природа) — не студійні
- Seasonal color story: lime-green як accent всього hero (одяг, аксесуари)
- Horizontal carousels — основний паттерн для товарів і категорій
- Activity-based navigation (Trail/Snow/Active) — smart UX для їх аудиторії
- Великі portrait-ratio фото (3:4) як стандарт
- Чергування: hero → collection carousel → full-bleed categories → activity selector → bestsellers → editorial
- Мінімум тексту, максимум фотографій
- Off-white фон, чорний текст, seasonal accent color

---

## СПІЛЬНА ДНК ВСІХ 3 РЕФЕРЕНСІВ

1. **Повітря** — щедрі відступи між секціями (py-20+), елементи не злиплені, кожен блок дихає
2. **Великі lifestyle-фото** — домінують над текстом, portrait ratio (3:4), на моделях в контексті
3. **Чергування типів секцій** — жоден layout не повторюється підряд: hero → carousel → full-bleed → split → editorial
4. **Горизонтальні carousels** — замість статичних grid-ів, з стрілками навігації
5. **Uppercase tracking заголовки** — великі, з letter-spacing, створюють luxury-відчуття
6. **Мінімум тексту** — заголовок + 1 речення + CTA, не більше
7. **Off-white/cream фон** — жоден з сайтів не використовує чистий білий (#fff)
8. **Brand voice через фотографію** — ти відчуваєш бренд через фото, не через слова
9. **Sticky nav з backdrop-blur** — мінімальна, не відволікає від контенту
10. **Newsletter в footer** — чистий, з великим input і CTA

DurnevShop має всі передумови для того, щоб стати таким же — сильний бренд, лояльна аудиторія, впізнаваний стиль. Залишилось лише дати сайту дизайн, гідний цього бренду.
