# 1С как иностранный язык

**Сравнительный справочник синтаксиса и архитектуры 1С для разработчиков, у которых уже есть опыт в Python, JavaScript или C#.**

[![release](https://img.shields.io/github/v/release/iMironRU/1c-razgovornik?label=релиз&color=blue)](https://github.com/iMironRU/1c-razgovornik/releases/latest)
[![license](https://img.shields.io/badge/лицензия-CC%20BY%204.0-lightgrey)](https://creativecommons.org/licenses/by/4.0/)
[![nightly](https://img.shields.io/github/actions/workflow/status/iMironRU/1c-razgovornik/build-nightly.yml?label=ночная%20сборка)](https://github.com/iMironRU/1c-razgovornik/actions/workflows/build-nightly.yml)

## Что это

Книга устроена в одну сторону: каждая конструкция объясняется сначала **как она есть в 1С** и почему устроена именно так, потом — аналогии с другими языками и ловушки при переходе. Это намеренная база сравнения: чтобы 1С выглядела не «странной версией Python», а самостоятельным языком со своей логикой.

Работает в обе стороны:

- **Кто приходит в 1С** — находит знакомые паттерны и узнаёт, где они ломаются.
- **Кто уходит из 1С** — видит, во что превращаются привычные конструкции в Python, JavaScript и C#.

Не учебник программирования с нуля и не справочник по платформенному API — только синтаксис и архитектурные концепции. Полные принципы — в [spec/constitution.md](spec/constitution.md).

## Где читать

- **Готовая версия** — [последний релиз](https://github.com/iMironRU/1c-razgovornik/releases/latest): EPUB, PDF A5, HTML, DOCX, FB2.
- **Онлайн** — [imironru.github.io/1c-razgovornik](https://imironru.github.io/1c-razgovornik).
- **В репозитории** — оглавление в [SUMMARY.md](SUMMARY.md), исходники глав в [chapters/](chapters/).

## Что внутри

| Глава | Что разбирается | Статус |
|---|---|---|
| [0. Предисловие](chapters/00_predislovie/00-01_dlya_kogo.md) | Для кого книга, как читать, что считаем общим знанием | review |
| [1. Природа языка](chapters/01_priroda_yazyka/01-01_paradigma.md) | Парадигма, типизация, типы модулей, контекст выполнения | review |
| [2. Переменные и примитивные типы](chapters/02_peremennye_i_tipy/02-01_peremennye.md) | Объявление, область видимости, строка, число, дата | review |
| [3. Коллекции](chapters/03_kollektsii/03-01_massiv.md) | Массив, структура, соответствие, таблица и дерево значений | review |
| [4. Управление потоком](chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md) | `Если`, тернарный `?()`, три цикла, `Прервать` / `Перейти` | review |
| 5. Процедуры и функции | _в работе_ | — |
| 6. Обработка ошибок | _в работе_ | — |
| 7. Асинхронность | _в работе_ | — |
| 8. Объекты и модули | _в работе_ | — |

Статусы параграфов: `draft` — черновик, `review` — на обкатке, `ready` — финальный. Релиз включает только `review` и `ready` (фильтр в [metadata.yaml](metadata.yaml)). Ночная сборка собирает всё, включая черновики.

## Как устроен параграф

Каждый параграф следует одной схеме:

1. Связь с предыдущим — одна-две фразы.
2. Конструкция в 1С: как пишется и почему так.
3. Таблица аналогий: 1С / Python / JavaScript / C#.
4. Блок «Ловушки при переходе» — отдельно для каждой стороны.
5. Якорная выноска с главной мыслью.

Подробности — в [docs/style-guide.md](docs/style-guide.md).

## Собрать локально

```bash
./book.sh build           # все форматы из metadata.yaml
./book.sh build review    # только review/ready — то, что попадает в релиз
./book.sh status          # прогресс по главам
```

Требования: `pandoc 3.5+`, `python3` + `pyyaml`, `mdbook` (для сайта), TeX Live с кириллическими шрифтами (для PDF).

## Структура репозитория

```
chapters/      — главы и параграфы (по одному .md на параграф)
spec/          — конституция, спецификация, журнал решений
docs/          — гайды автора (стиль, рабочий процесс)
.github/       — release- и nightly-сборки, проверка обновлений шаблона
book.sh        — единая точка входа
metadata.yaml  — версия, форматы, фильтры релиза
```

Шаблон сборки — [iMironRU/book-template](https://github.com/iMironRU/book-template); обновления приходят как issue.

## Лицензия

Текст книги — [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Скрипты сборки — по лицензии шаблона.

Автор — [Александр Мирошниченко](https://github.com/iMironRU).
