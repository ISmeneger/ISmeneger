# Илья Сидорычев | QA Automation Engineer — Java / Python

Разрабатываю **UI- и REST API-автотесты на Java и Python**. В портфолио — проекты UI/API-автоматизации American Eagle на Java и Python, отдельная коллекция API-тестов в **Postman с JavaScript-проверками**, самостоятельный проект **SQL-тестирования на PostgreSQL и Docker**, а также репозиторий по ручному тестированию, тест-дизайну и QA-документации. Настроены GitHub Actions и публикация Allure Report для Java- и Python-проектов.

Ищу первую коммерческую позицию **Junior QA / Automation QA Engineer**. Санкт-Петербург · рассматриваю удалённый, офисный и гибридный формат, а также стажировку.

**[Telegram](https://t.me/Ilya_S_1985)** · **[Email](mailto:ISmeneger@yandex.ru)** · **[Хабр Карьера](https://career.habr.com/ismeneger)**

## Основные проекты

### [American Eagle — Java UI & API Automation](https://github.com/ISmeneger/American_Eagle_java_automation)

**Java 21 · JUnit 5 · Selenium WebDriver · REST Assured · Gradle · Allure · GitHub Actions**

Проект начался как выпускная работа по Java AQA и затем был существенно расширен самостоятельно.

- **API:** Token, Browse, Inventory, Bag; позитивные и негативные проверки авторизации; E2E-сценарий добавления, изменения и удаления товара в корзине.
- **Архитектура:** Page Objects, Components и Steps для UI; Controllers и DTO для API; JUnit 5 Extensions, Owner, AssertJ.
- **Инженерные решения:** динамический выбор доступных товаров и SKU; Awaitility для ожидания обновления состояния API; обработка региональных и маркетинговых окон; отдельная обработка известного дефекта через `KnownDefectExtension`.
- **CI и отчётность:** отдельные API/UI jobs, Selenium Standalone Chrome для удалённого запуска, GitHub Secrets, сохранение артефактов и объединение результатов в Allure Report с историей.

**[Код и инструкция запуска](https://github.com/ISmeneger/American_Eagle_java_automation)** · **[CI-запуски](https://github.com/ISmeneger/American_Eagle_java_automation/actions)** · **[Allure Report](https://ismeneger.github.io/American_Eagle_java_automation/)**

### [American Eagle — Python UI & API Automation](https://github.com/ISmeneger/American_Eagle_python_automation)

**Python 3.12 · Pytest · Selenium WebDriver · Requests · Allure · GitHub Actions**

Самостоятельный проект вне учебной программы: реализовал автоматизацию того же продукта на Python, адаптировав архитектуру и управление тестовыми данными под Pytest.

- **API:** отдельные клиенты для Token, Browse, Inventory и Bag; позитивные и негативные сценарии; проверка жизненного цикла корзины и нескольких разных товаров.
- **UI:** поиск, каталог, фильтрация, сортировка, формы и корзина; проверка цены товара, количества и итоговой стоимости.
- **Инженерные решения:** fixtures для подготовки и очистки состояния; динамические данные; explicit waits, `safe_click()` и повторное получение элементов после изменения DOM; централизованная обработка cookies, региональных окон и двух типов Bloomreach popup (включая Shadow DOM); `Decimal` для проверки цен.
- **CI и отчётность:** независимые API/UI jobs, headless Chrome, GitHub Secrets, единый Allure Report с историей и диагностическими вложениями для UI-падений. **Последний подтверждённый CI от 16.10.2026:** 52 сценария — 47 passed, 4 skipped, 1 xfailed, без неожиданных падений.

**[Код и инструкция запуска](https://github.com/ISmeneger/American_Eagle_python_automation)** · **[CI-запуски](https://github.com/ISmeneger/American_Eagle_python_automation/actions)** · **[Allure Report](https://ismeneger.github.io/American_Eagle_python_automation/)**

В обоих проектах есть тест-планы и описание ограничений внешнего сайта. Сценарии, заблокированные anti-bot-защитой, и известные особенности поведения отмечены отдельно. Результаты запусков доступны в CI и Allure. American Eagle — динамический production-сайт, поэтому повторные локальные и CI-запуски могут потребовать адаптации тестов к изменениям интерфейса, товаров или защиты.

### [American Eagle — Postman API Testing](https://github.com/ISmeneger/American_Eagle_Postman_API_Tests)

**Postman · JavaScript · REST API · OAuth 2.0 · Bearer Token · Postman Vault**

Самостоятельный проект автоматизированного тестирования REST API American Eagle в Postman, дополняющий Java- и Python-автоматизацию.

- **API и E2E:** 18 запросов в трёх наборах — Positive E2E, Negative Tests и Utilities. Проверка полного жизненного цикла гостевой корзины: получение токена, добавление товаров, изменение количества, проверка содержимого и удаление.
- **Негативные сценарии:** отсутствие авторизации, неверный Bearer Token, некорректный SKU, отсутствие обязательного заголовка и недопустимое количество товара. Проверяются HTTP-статусы `400`, `401` и `422`.
- **Автоматизация:** JavaScript-проверки ответов, динамические переменные Postman, общий pre-request script для автоматического обновления гостевого токена. Учётные данные хранятся локально в Postman Vault.
- **Результаты:** подтверждённый локальный запуск Postman Collection Runner **19.10.2026 — 18 запросов, 124/124 успешных проверок, 0 ошибок**. В репозитории представлены коллекция, инструкция запуска, документация на русском и английском языках и скриншот результатов.

**[Коллекция и документация](https://github.com/ISmeneger/American_Eagle_Postman_API_Tests)** · **[Результаты запуска](https://github.com/ISmeneger/American_Eagle_Postman_API_Tests/blob/main/images/postman-runner-results.png)**

### [American Eagle — QA Test Documentation](https://github.com/ISmeneger/QA_Test_Documentation)

**Manual QA · Анализ требований · Тест-дизайн · Тест-кейсы · Чек-листы · Матрица трассируемости**

Самостоятельный проект по ручному тестированию American Eagle, дополняющий Java- и Python-автоматизацию.

- **Документация:** тест-план, проверяемые гипотезы требований, чек-листы, 20 подробных тест-кейсов, журналы выполнения и итоговые отчёты.
- **Ручное выполнение 14.10.2026:** 20 проверок — 18 Passed, 2 Needs Clarification. Неоднозначное поведение поиска не выдаётся за подтверждённый дефект без официальных требований.
- **Трассируемость:** матрица требований и сопоставление ручных сценариев с реализацией автотестов на Java и Python.

**[Документация и результаты](https://github.com/ISmeneger/QA_Test_Documentation)** · **[Матрица трассируемости](https://github.com/ISmeneger/QA_Test_Documentation/blob/main/coverage/REQUIREMENTS_TRACEABILITY_MATRIX.md)** · **[Аудит автоматизации](https://github.com/ISmeneger/QA_Test_Documentation/blob/main/automation/AUTOMATION_COVERAGE_AUDIT.md)**

### [American Eagle — SQL & Database Testing](https://github.com/ISmeneger/American_Eagle_SQL_QA)

**PostgreSQL 16 · SQL · Docker · DBeaver · PowerShell · Database Testing**

Самостоятельный SQL-проект для практики тестирования баз данных на примере учебной модели интернет-магазина American Eagle. Подготовил локальную PostgreSQL-базу с синтетическими данными, воспроизводимыми SQL-проверками и автоматизированным негативным сценарием.

- **База данных:** 8 связанных таблиц — товары, категории, складские остатки, покупатели, корзины и заказы. Проверка связей и целостности данных.
- **SQL-тестирование:** 10 QA-сценариев с использованием `SELECT`, `JOIN`, `GROUP BY`, `HAVING`, агрегатных функций, подзапросов и CTE. Проверка стоимости корзин и заказов, доступности товаров и корректности данных.
- **Негативное тестирование:** проверка ограничения `CHECK`, обработка ожидаемой ошибки PostgreSQL `SQLSTATE 23514`, контроль сохранности исходных данных и откат транзакций через `ROLLBACK`.
- **Окружение:** PostgreSQL 16 в Docker, работа с базой через DBeaver, PowerShell-скрипт для развёртывания учебного стенда.
- **Результаты:** 10 QA-сценариев дали ожидаемые результаты; контрольный запуск SQL-файлов выполнен успешно. В репозитории представлены SQL-код, документация и скриншоты DBeaver.

Проект использует автономную учебную модель с синтетическими данными и не предполагает доступа к производственной базе American Eagle.

**[SQL-запросы и инструкция запуска](https://github.com/ISmeneger/American_Eagle_SQL_QA)** · **[Результаты тестирования](https://github.com/ISmeneger/American_Eagle_SQL_QA/blob/main/docs/SQL_TESTING.md)**

## Учебная практика

### [ИТМО — DemoQA Python UI Automation](https://github.com/ISmeneger/ITMO_Automation_Demoqa)

**Python · Pytest · Selenium WebDriver · Page Object Model**

Первый учебный проект по UI-автоматизации, выполненный на курсе ИТМО и позднее доработанный для портфолио.

- Формы, alerts, модальные окна, вкладки, каталог учебных элементов и Web Tables: добавление, редактирование, удаление, поиск и пагинация.
- Page Objects и Components, явные ожидания, отдельный браузер для каждого теста, очистка React-полей и диагностика UI-падений.
- Подтверждённый локальный прогон **13.10.2026: 60 passed, 2 xfailed** — 50 успешных UI-сценариев и 10 проверок вспомогательной логики. Два strict xfail фиксируют воспроизведённые дефекты внешнего сайта.

**[Код и инструкция запуска](https://github.com/ISmeneger/ITMO_Automation_Demoqa)** · **[Известные дефекты и ограничения](https://github.com/ISmeneger/ITMO_Automation_Demoqa/blob/master/KNOWN_ISSUES.md)**

## Практические навыки

| Направление | Инструменты и подходы |
|---|---|
| Java AQA | Java, JUnit 5, REST Assured, Selenium, Gradle, AssertJ, Awaitility |
| Python AQA | Python, Pytest, Requests, Selenium, fixtures, markers |
| REST API | HTTP, REST, JSON, Postman, JavaScript assertions, OAuth 2.0, Bearer Token, Postman Vault, позитивные и негативные проверки, E2E-сценарии |
| Архитектура тестов | Page Object Model, Components, Steps, API clients / Controllers, DTO |
| CI/CD и отчётность | GitHub Actions: запуск тестов, артефакты, Secrets; Allure Report, публикация отчётов через GitHub Pages |
| SQL / Database Testing | PostgreSQL, MySQL, DBeaver, Docker; SELECT, JOIN, GROUP BY, HAVING, подзапросы, CTE, проверка целостности данных, транзакции, негативное тестирование |
| QA-документация | Анализ требований, тест-планы, чек-листы, тест-кейсы, баг-репорты, матрицы трассируемости |
| Разработка | Git / GitHub, IntelliJ IDEA, PyCharm, Chrome DevTools |

## Профессиональный опыт и переход в QA

До перехода в QA работал в инженерии, производстве и предпринимательстве. В **ОАО «Автокран»** занимался технологическими процессами и технической документацией, работал в КОМПАС, ЛОЦМАН, ВЕРТИКАЛЬ и 1С. На **Костромской ГРЭС** контролировал состояние оборудования и рабочие параметры, выявлял отклонения.

С апреля 2023 года работаю инженером в **ООО «Аварит»**: анализирую требования и исходные данные, выполняю расчёты систем электрообогрева кровель, площадок, трубопроводов, резервуаров и полов, подбираю оборудование. Готовлю техническую и тендерную документацию, взаимодействую с заказчиками и поставщиками.

Опыт предпринимательства и B2B-продаж дал практику организации процессов, переговоров и работы с заказчиками.

В автоматизации тестирования применяю инженерный подход: разбираюсь в требованиях, проверяю результат, учитываю ограничения и собираю данные для анализа ошибок. Особенно интересны задачи тестирования веб-сервисов и программных решений для **энергетики и промышленности**.

## Образование

- **2025 — авторский курс Геннадия Чурсова по автоматизации тестирования на Java.** Выпускная работа — [автоматизация тестирования American Eagle](https://github.com/ISmeneger/American_Eagle_java_automation). [Программа курса](https://topsycreed.github.io/free-java-automation-course/) · [GitHub автора](https://github.com/topsycreed) · [Telegram автора](https://t.me/chursovQA).
- **2024 — Университет ИТМО, Санкт-Петербург.** Ручное и автоматизированное тестирование ПО на Python. Дополнительно — курсы по ручному и автоматизированному тестированию на Stepik.
- **2023 — ООО «Национальный институт сертификации и оценки качества», Москва.** Повышение квалификации: «Анализ данных как основа цифровой трансформации процессов управления организацией». Изучал SQL, PostgreSQL и MySQL.
- **2022 — Российский экономический университет имени Г. В. Плеханова.** Профессиональная переподготовка: «Процедурно-ориентированное программирование в прикладных задачах анализа данных в экономике». Диплом с правом ведения профессиональной деятельности в сфере программирования на Python для решения задач бизнес-анализа.
- **2010 — Ивановский государственный энергетический университет имени В. И. Ленина.** Квалификация: менеджер.
- **2009 — Ивановский государственный энергетический университет имени В. И. Ленина.** Квалификация: инженер.

## Контакты

- Telegram: [@Ilya_S_1985](https://t.me/Ilya_S_1985)
- Email: [ISmeneger@yandex.ru](mailto:ISmeneger@yandex.ru)
- Телефон: +7 (901) 286-40-78
- Хабр Карьера: [career.habr.com/ismeneger](https://career.habr.com/ismeneger)
