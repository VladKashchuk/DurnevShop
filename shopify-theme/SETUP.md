# DURNEV Shopify Theme — Custom Sections

## Що всередині

Кастомні секції для головної сторінки DurnevShop, адаптовані під Shopify Online Store 2.0.

```
shopify-theme/
├── sections/
│   ├── durnev-hero-split.liquid       — Hero split screen (текст + фото)
│   ├── durnev-brand-statement.liquid  — Brand statement (одне речення)
│   ├── durnev-featured-carousel.liquid — Горизонтальний carousel товарів
│   ├── durnev-lifestyle-banner.liquid — Full-bleed lifestyle фото з overlay
│   ├── durnev-categories-grid.liquid  — Asymmetric grid категорій (2fr 1fr)
│   ├── durnev-editorial-split.liquid  — Editorial 50/50 split (About)
│   ├── durnev-social-grid.liquid      — Instagram / social proof grid
│   └── durnev-newsletter.liquid       — Newsletter з dark background
├── snippets/
│   └── durnev-base-styles.liquid      — Shared CSS variables, buttons, animations
├── templates/
│   └── index.json                     — Homepage template (порядок секцій)
└── SETUP.md                           — Цей файл
```

## Як встановити

### 1. Підготовка (якщо ще не зроблено)
```bash
# Переконайся що є Shopify CLI
shopify version

# Pull Dawn тему з dev store
shopify theme pull --store YOUR-STORE.myshopify.com
```

### 2. Скопіювати файли
```bash
# З кореня проекту:
cp shopify-theme/snippets/*.liquid YOUR-THEME/snippets/
cp shopify-theme/sections/*.liquid YOUR-THEME/sections/
cp shopify-theme/templates/index.json YOUR-THEME/templates/index.json
```

### 3. Додати Google Fonts

В `layout/theme.liquid`, перед `</head>`, додай:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Outfit:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

### 4. Announcement Bar

Використовуй вбудований Dawn announcement bar:
- Theme Editor > Header > Announcement bar
- Текст: `БЕЗКОШТОВНА ДОСТАВКА ПО УКРАЇНІ ВІД 2000 ГРН`
- Color scheme: dark

### 5. Запустити dev preview
```bash
shopify theme dev --store YOUR-STORE.myshopify.com
# Відкрий localhost:9292
```

### 6. Налаштувати секції

Всі секції мають schema з merchant-editable settings.
В Theme Editor (Customize) для головної сторінки:
- Кожна секція має плейсхолдер зображення (picsum.photos)
- Заміни на реальні фото через Image Picker
- Featured Carousel: обери колекцію "Bestsellers" або іншу
- Categories Grid: додай посилання на колекції
- Social Grid: додай фото з Instagram

### 7. Перевірити та задеплоїти
```bash
# Валідація Liquid
shopify theme check

# Deploy
shopify theme push --store YOUR-STORE.myshopify.com
```

## Дизайн-система

Всі CSS tokens знаходяться в `snippets/durnev-base-styles.liquid`:
- Кольори: off-white #FAFAF8, text #18181b, secondary #71717a
- Шрифти: Outfit (display), Inter (body)
- Spacing: clamp() для fluid sizing
- Motion: cubic-bezier(0.16, 1, 0.3, 1)
- Buttons: pill shape, uppercase, tracking

## Що НЕ включено (використовуй Dawn defaults)

- Header / Navigation — налаштуй через Dawn Theme Editor
- Footer — налаштуй через Dawn Theme Editor
- Announcement Bar — Dawn built-in
- Product pages — Dawn defaults
- Collection pages — Dawn defaults
- Cart — Dawn defaults

## Що потрібно доробити на Shopify стороні

1. Завантажити фото товарів та lifestyle зображення
2. Створити колекції (Bestsellers, Hoodies, T-shirts, Accessories)
3. Налаштувати Dawn header (logo, navigation links)
4. Налаштувати Dawn footer (links, social, contacts)
5. Підключити email сервіс для newsletter (Klaviyo / Shopify Email)

## Перегляд дизайну (HTML mockup)

Файл `../index.html` — статичний HTML прототип з повним дизайном.
Відкрий в браузері для reference при налаштуванні Shopify секцій.
