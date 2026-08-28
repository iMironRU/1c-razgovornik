# Реестр блоков кода

> Файл собирается автоматически. Не править руками — правьте разметку ограждений
> в главах и пересоберите.

Каждый блок кода в книге отнесён к одной кучке. Кучка определяется **прогоном через
ядро [BSLexicon](https://github.com/iMironRU/BSLexicon)**, а не по виду листинга:
блок либо исполняется, либо нет, и причина известна точно.

| Кучка | Блоков | Что это |
|---|---:|---|
| `песочница` | 23 | исполняется в тренажёре — кнопка «Запустить», проверяется гейтом |
| `набросок` | 27 | чистый язык, но пока не исполняется: не хватает контекста или точек с запятой |
| `платформа` | 1 | запросы, клиент-сервер, справочники — тренажёр этого не умеет по замыслу |
| `шаблон` | 0 | форма конструкции с плейсхолдерами в угловых скобках |
| `ловушка` | 0 | код, показанный нарочно неверным или бесконечным |
| `текст` | 18 | не код: таблица данных, вывод программы, дерево, схема, проза |
| **всего** | **69** | |

## Что с этим делать

**`песочница`** — готово. Гейт следит, чтобы оставалось исполнимым.

**`набросок`** — резерв. Каждый такой блок может стать песочницей, если дописать
недостающее. Но это правка **текста книги**, а не разметки: где-то контекст задан
в соседнем абзаце нарочно, и дублировать его в листинге — испортить подачу.
Решение по каждому — авторское.

**`платформа`**, **`шаблон`**, **`ловушка`** — так и останутся. Машина их не
проверит: тренажёр не знает языка запросов, плейсхолдер не является кодом,
а ловушка неисправна намеренно.

**`текст`** — вообще не код.

## `песочница` — 23

| Где | Первая строка | Почему |
|---|---|---|
| [chapters/01_priroda_yazyka/01-03_tipizaciya.md:9](../chapters/01_priroda_yazyka/01-03_tipizaciya.md) | `// 1С` | исполняется |
| [chapters/01_priroda_yazyka/01-04_tipy_moduley.md:24](../chapters/01_priroda_yazyka/01-04_tipy_moduley.md) | `// Общий модуль «РаботаСЦенами»` | исполняется |
| [chapters/02_peremennye_i_tipy/02-01_peremennye.md:11](../chapters/02_peremennye_i_tipy/02-01_peremennye.md) | `Процедура РассчитатьСтоимость()` | исполняется |
| [chapters/02_peremennye_i_tipy/02-01_peremennye.md:22](../chapters/02_peremennye_i_tipy/02-01_peremennye.md) | `Перем СчётчикВызовов;   // объявлена на уровне модуля` | исполняется |
| [chapters/02_peremennye_i_tipy/02-03_stroka.md:23](../chapters/02_peremennye_i_tipy/02-03_stroka.md) | `Результат = "Итого: " + 1500;   // "Итого: 1500" — число при` | исполняется |
| [chapters/02_peremennye_i_tipy/02-03_stroka.md:40](../chapters/02_peremennye_i_tipy/02-03_stroka.md) | `СтрДлина("привет")              // 6` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/02_peremennye_i_tipy/02-04_chislo.md:9](../chapters/02_peremennye_i_tipy/02-04_chislo.md) | `Цена = 1500;       // целое` | исполняется |
| [chapters/02_peremennye_i_tipy/02-05_bulevo.md:9](../chapters/02_peremennye_i_tipy/02-05_bulevo.md) | `Флаг = Истина;` | исполняется |
| [chapters/02_peremennye_i_tipy/02-06_neopredeleno_null.md:11](../chapters/02_peremennye_i_tipy/02-06_neopredeleno_null.md) | `Перем Х;` | исполняется |
| [chapters/02_peremennye_i_tipy/02-06_neopredeleno_null.md:25](../chapters/02_peremennye_i_tipy/02-06_neopredeleno_null.md) | `// Null появляется при работе с запросами и реквизитами` | исполняется |
| [chapters/02_peremennye_i_tipy/02-07_data.md:11](../chapters/02_peremennye_i_tipy/02-07_data.md) | `Д1 = '20240115';           // 15 января 2024 года, время 00:` | исполняется |
| [chapters/03_kollektsii/03-01_massiv.md:9](../chapters/03_kollektsii/03-01_massiv.md) | `// Создание` | исполняется |
| [chapters/03_kollektsii/03-01_massiv.md:34](../chapters/03_kollektsii/03-01_massiv.md) | `// По коллекции — предпочтительно` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/03_kollektsii/03-04_spisok.md:9](../chapters/03_kollektsii/03-04_spisok.md) | `СписокТоваров = Новый СписокЗначений;` | исполняется |
| [chapters/03_kollektsii/03-05_tablitsa.md:9](../chapters/03_kollektsii/03-05_tablitsa.md) | `// Создание и определение структуры` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/04_upravlenie_potokom/04-03_cikl_dlya_po.md:11](../chapters/04_upravlenie_potokom/04-03_cikl_dlya_po.md) | `Для Сч = 1 По 3 Цикл` | исполняется |
| [chapters/04_upravlenie_potokom/04-03_cikl_dlya_po.md:25](../chapters/04_upravlenie_potokom/04-03_cikl_dlya_po.md) | `Для Сч = 0 По Товары.Количество() - 1 Цикл` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/04_upravlenie_potokom/04-03_cikl_dlya_po.md:52](../chapters/04_upravlenie_potokom/04-03_cikl_dlya_po.md) | `Предел = 3;` | исполняется |
| [chapters/04_upravlenie_potokom/04-04_cikl_dlya_kazhdogo.md:9](../chapters/04_upravlenie_potokom/04-04_cikl_dlya_kazhdogo.md) | `Для Каждого Товар Из Товары Цикл` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/04_upravlenie_potokom/04-04_cikl_dlya_kazhdogo.md:53](../chapters/04_upravlenie_potokom/04-04_cikl_dlya_kazhdogo.md) | `// Ошибка: удаление во время обхода` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/04_upravlenie_potokom/04-05_cikl_poka.md:9](../chapters/04_upravlenie_potokom/04-05_cikl_poka.md) | `Остаток = 100;` | исполняется |
| [chapters/04_upravlenie_potokom/04-05_cikl_poka.md:21](../chapters/04_upravlenie_potokom/04-05_cikl_poka.md) | `Сч = Товары.Количество() - 1;` | исполняется — рядом лежит вариант с точками с запятой |
| [chapters/04_upravlenie_potokom/04-05_cikl_poka.md:52](../chapters/04_upravlenie_potokom/04-05_cikl_poka.md) | `Очередь = Новый Массив;        // пустая` | исполняется |

## `набросок` — 27

| Где | Первая строка | Почему |
|---|---|---|
| [chapters/02_peremennye_i_tipy/02-01_peremennye.md:36](../chapters/02_peremennye_i_tipy/02-01_peremennye.md) | `Уровень             1С                  Python              ` | lexer: Неизвестный символ «─» |
| [chapters/02_peremennye_i_tipy/02-03_stroka.md:9](../chapters/02_peremennye_i_tipy/02-03_stroka.md) | `// Однострочная` | lexer: Незакрытая строковая константа |
| [chapters/02_peremennye_i_tipy/02-03_stroka.md:31](../chapters/02_peremennye_i_tipy/02-03_stroka.md) | `"Привет" = "привет"   // Истина` | parser: Неожиданный токен «Привет» |
| [chapters/02_peremennye_i_tipy/02-04_chislo.md:19](../chapters/02_peremennye_i_tipy/02-04_chislo.md) | `10 / 3    // 3.333... (не 3)` | parser: Неожиданный токен «10» |
| [chapters/02_peremennye_i_tipy/02-04_chislo.md:25](../chapters/02_peremennye_i_tipy/02-04_chislo.md) | `Цел(10 / 3)              // 3` | parser: Ожидалось «;», получено «10» |
| [chapters/02_peremennye_i_tipy/02-07_data.md:18](../chapters/02_peremennye_i_tipy/02-07_data.md) | `Завтра = СегодняДата + 86400;      // + одни сутки (86400 се` | чистый язык, не хватает контекста: СегодняДата |
| [chapters/02_peremennye_i_tipy/02-07_data.md:25](../chapters/02_peremennye_i_tipy/02-07_data.md) | `ТекущаяДата()                   // текущая дата и время` | parser: Ожидалось «;», получено «НачалоДня» |
| [chapters/02_peremennye_i_tipy/02-07_data.md:39](../chapters/02_peremennye_i_tipy/02-07_data.md) | `Операция              1С                          Python` | lexer: Неизвестный символ «─» |
| [chapters/03_kollektsii/03-02_struktura.md:11](../chapters/03_kollektsii/03-02_struktura.md) | `// Создание — пустая` | runtime: Значение типа «Структура» не поддерживает об |
| [chapters/03_kollektsii/03-02_struktura.md:49](../chapters/03_kollektsii/03-02_struktura.md) | `// Вместо функции с множеством параметров` | чистый язык, не хватает контекста: СсылкаНаКлиента |
| [chapters/03_kollektsii/03-03_sootvetstvie.md:9](../chapters/03_kollektsii/03-03_sootvetstvie.md) | `// Создание` | parser: Неожиданный токен «.» |
| [chapters/03_kollektsii/03-05_tablitsa.md:95](../chapters/03_kollektsii/03-05_tablitsa.md) | `Возможность              ТЗ (1С)        DataFrame (Python)  ` | lexer: Неизвестный символ «#» |
| [chapters/03_kollektsii/03-06_derevo.md:9](../chapters/03_kollektsii/03-06_derevo.md) | `Дерево = Новый ДеревоЗначений;` | runtime: «Новый»: неизвестный тип «ДеревоЗначений» |
| [chapters/03_kollektsii/03-07_fiksirovannye.md:9](../chapters/03_kollektsii/03-07_fiksirovannye.md) | `// Обычный массив → фиксированный` | lexer: Неизвестный символ «…» |
| [chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md:11](../chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md) | `Если Сумма > 1000 Тогда` | чистый язык, не хватает контекста: Сумма |
| [chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md:25](../chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md) | `Если Клиент.Постоянный И Сумма > 1000 Тогда` | чистый язык, не хватает контекста: Клиент |
| [chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md:35](../chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md) | `// Ошибка: Количество() возвращает Число, а не Булево` | чистый язык, не хватает контекста: Товары |
| [chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md:53](../chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md) | `Если Статус = "Новый" Тогда` | чистый язык, не хватает контекста: Статус |
| [chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md:67](../chapters/04_upravlenie_potokom/04-01_uslovnyy_operator.md) | `ЦветаПоСтатусу = Новый Соответствие;` | чистый язык, не хватает контекста: Статус |
| [chapters/04_upravlenie_potokom/04-02_ternarnyy_operator.md:11](../chapters/04_upravlenie_potokom/04-02_ternarnyy_operator.md) | `Скидка = ?(Сумма > 1000, 0.10, 0);` | чистый язык, не хватает контекста: Сумма |
| [chapters/04_upravlenie_potokom/04-02_ternarnyy_operator.md:19](../chapters/04_upravlenie_potokom/04-02_ternarnyy_operator.md) | `// Опасно: деление выполнится ДАЖЕ когда Количество = 0` | чистый язык, не хватает контекста: Количество |
| [chapters/04_upravlenie_potokom/04-02_ternarnyy_operator.md:26](../chapters/04_upravlenie_potokom/04-02_ternarnyy_operator.md) | `Если Количество <> 0 Тогда` | чистый язык, не хватает контекста: Количество |
| [chapters/04_upravlenie_potokom/04-04_cikl_dlya_kazhdogo.md:32](../chapters/04_upravlenie_potokom/04-04_cikl_dlya_kazhdogo.md) | `// Массив, Список значений — элемент это само значение` | чистый язык, не хватает контекста: Товары |
| [chapters/04_upravlenie_potokom/04-06_prervat_prodolzhit.md:9](../chapters/04_upravlenie_potokom/04-06_prervat_prodolzhit.md) | `Для Каждого Товар Из Товары Цикл` | чистый язык, не хватает контекста: Товары |
| [chapters/04_upravlenie_potokom/04-06_prervat_prodolzhit.md:27](../chapters/04_upravlenie_potokom/04-06_prervat_prodolzhit.md) | `Найдено = Ложь;` | чистый язык, не хватает контекста: Заказы |
| [chapters/04_upravlenie_potokom/04-07_perekhod.md:9](../chapters/04_upravlenie_potokom/04-07_perekhod.md) | `Сч = 0;` | lexer: Неизвестный символ «~» |
| [chapters/04_upravlenie_potokom/04-07_perekhod.md:29](../chapters/04_upravlenie_potokom/04-07_perekhod.md) | `Для Каждого Заказ Из Заказы Цикл` | lexer: Неизвестный символ «~» |

## `платформа` — 1

| Где | Первая строка | Почему |
|---|---|---|
| [chapters/01_priroda_yazyka/01-05_kontekst.md:67](../chapters/01_priroda_yazyka/01-05_kontekst.md) | `&НаСервере` | платформенные объекты |

## `текст` — 18

_Списком не приводится: это не код._

