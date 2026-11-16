# Строка · Strokka

**AI-платформа поиска компаний и контактов по базе организаций РФ.**
2.4 млн компаний · семантический поиск на естественном языке · фильтры по email, телефонам, Telegram, ВКонтакте · экспорт в CSV/CRM · API.

🌐 [strokka.com](https://strokka.com) · 🖥 [Кабинет](https://app.strokka.com) · 📚 [API-документация](https://docs.strokka.com) · ✉️ vlad@strokka.com

---

## Продукт

| | |
|---|---|
| 🔎 **Поиск** | Гибридный (вектор + полнотекст), SQL-режим, поиск по сущностям. Запрос обычными словами: «производители мебели с email в Москве» |
| 🤖 **Агент «Скрепка»** | AI-агент собирает выборки компаний диалогом, применяет фильтры и готовит выгрузку |
| 📇 **Данные** | Сайты, описания, города, отрасли, email, телефоны, Telegram, ВК, WhatsApp и другие публичные каналы |
| 📤 **Экспорт и API** | Выгрузка контактов в CSV/CRM, REST API с ключами, MCP для AI-инструментов |

## Репозитории

| Репозиторий | Что это | Стек |
|---|---|---|
| [strokka-app](https://github.com/strokka-com/strokka-app) | Кабинет: поиск, агент, экспорт, биллинг — [app.strokka.com](https://app.strokka.com) | Next.js 16 · React 19 · better-auth |
| [strokka-landing](https://github.com/strokka-com/strokka-landing) | Публичный сайт, SEO-каталог баз (300+ LP), блог — [strokka.com](https://strokka.com) | Next.js 16 · Tailwind 4 · MDX |
| [strokka-server](https://github.com/strokka-com/strokka-server) | Backend: Classic API + Agent + MCP | FastAPI · YDB · Redis |
| [strokka-docs](https://github.com/strokka-com/strokka-docs) | Документация API — [docs.strokka.com](https://docs.strokka.com) | Next.js · MDX · OpenAPI |
| [strokka-services](https://github.com/strokka-com/strokka-services) | Data pipeline: dns → http → browser → valid → view, ИНН/ЕГРЮЛ enrich | Python · Playwright · YDB |
| [strokka-marketing](https://github.com/strokka-com/strokka-marketing) | Маркетинговые агенты: поиск компаний, письма, отправка | Python |

## Архитектура

```
landing (strokka.com)      → публичный сайт + SEO
app (app.strokka.com)      → кабинет
  /api/v1/*                → Classic API (FastAPI)
  /api/agent/v1/*          → Agent API
server                     → YDB: каталог, пользователи, векторы, полнотекст · Redis
services                   → сбор и обогащение данных → каталог YDB
docs (docs.strokka.com)    → OpenAPI + MDX
```

Контакты маскируются по умолчанию; полный доступ — кредиты или API-ключ. Данные собираются из открытых источников.

---

ООО «Строка» · Санкт-Петербург · [Telegram](https://t.me/strokka_com) · [ВКонтакте](https://vk.ru/strokka_com) · [Spark](https://spark.ru/startup/strokka)
