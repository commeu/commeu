<div align="center">
  <img src="banner.svg" alt="Артём — разработчик" width="100%">
</div>

<p align="center">
  <a href="https://t.me/mysoldroom"><img src="https://img.shields.io/badge/Telegram-@mysoldroom-26A5E4?style=flat-square&logo=telegram&logoColor=white" alt="Telegram"></a>
  <img src="https://img.shields.io/badge/Москва-UTC%2B3-1e293b?style=flat-square" alt="Москва, UTC+3">
  <img src="https://img.shields.io/badge/открыт_к_предложениям-удалённо-22d3ee?style=flat-square" alt="Открыт к предложениям">
</p>

## Обо мне

- **1,5 года в IT:** сетевая инфраструктура и разработка ПО.
- **Делаю браузерные игры** на TypeScript и JavaScript для Яндекс Игр: механики, интерфейс, интеграция с SDK, релизная сборка и автотесты.
- **Строю разработку вокруг AI-агентов.** Агенты работают по письменным правилам и ведут журнал, а каждое их изменение проходит автотесты. Задачи, архитектура и приёмка за мной.
- **Ищу удалённую работу:** разработка, автоматизация и тестирование, инфраструктура и DevOps.

## Стек

**Языки**<br>
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black">
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">

**Фронтенд и игры**<br>
<img src="https://img.shields.io/badge/HTML5_Canvas-E34F26?style=flat-square&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/Web_Audio_API-334155?style=flat-square">
<img src="https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white">
<img src="https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white">

**Тесты, CI и инфраструктура**<br>
<img src="https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white">
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white">
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white">
<img src="https://img.shields.io/badge/Сетевая_инфраструктура-0f766e?style=flat-square">

**AI-разработка**<br>
<img src="https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=claude&logoColor=white">
<img src="https://img.shields.io/badge/OpenAI_Codex-412991?style=flat-square&logo=openai&logoColor=white">
<img src="https://img.shields.io/badge/ChatGPT-10A37F?style=flat-square&logo=openai&logoColor=white">

## Проекты

> Репозитории закрытые: игры готовятся к публикации. Код и демо покажу по запросу в Telegram.

### Лисий рейд / Fox Raid · `v1.19.2`

Стелс-аркада для Яндекс Игр: лис пробирается на охраняемую территорию, освобождает питомцев и уходит от охраны до конца таймера.

<p align="center">
  <img src="assets/fox-raid/gameplay.gif" alt="Геймплей Fox Raid" width="100%">
</p>

<table>
  <tr>
    <td width="50%"><img src="assets/fox-raid/camp.jpg" alt="Лагерь"><br><sub>Лагерь: прогресс, рейд дня, событие недели</sub></td>
    <td width="50%"><img src="assets/fox-raid/boss.jpg" alt="Босс-рейд"><br><sub>Босс-рейд: прожектор с прогнозом следующего хода</sub></td>
  </tr>
  <tr>
    <td width="50%"><img src="assets/fox-raid/siren.jpg" alt="Тревога"><br><sub>Тревога: сирену можно успеть выключить</sub></td>
    <td width="50%"><img src="assets/fox-raid/collection.jpg" alt="Коллекция"><br><sub>Коллекция: 30 питомцев со звёздами и способностями</sub></td>
  </tr>
</table>

- **Без движков:** чистый JavaScript и Canvas, ноль production-зависимостей; сборка в один автономный HTML-файл и ZIP для платформы.
- **Контент:** 5 зон, 30 питомцев, процедурные контракты, ежедневные и недельные события, бесконечный режим, босс-рейд, 22 медали, RU/EN.
- **Производительность:** автоматические профили качества с лимитом пикселей, кэш спрайтов с ограничением памяти, симуляция 60 Гц отдельно от отрисовки.
- **Надёжность данных:** облачные сохранения по постоянному ID игрока с защитой от гонок при смене аккаунта.
- **Доступность:** крупный текст, высокий контраст, уменьшенные анимации, режим для левой руки; проверка 7 размеров экрана от 320×568 до 1280×720.

| Набор тестов | Что проверяет |
|---|---|
| `npm test` | механика, сохранения, качество графики |
| `test:browser` | управление, сценарии SDK, восстановление аккаунта, доступность (Playwright) |
| `codex:release` | собранные HTML и ZIP: реальный ввод, reload, отсутствие тестового кода |
| `test:local-layouts` | 28 сочетаний RU/EN × 7 размеров экрана |
| `test:progression` | полное прохождение всех зон автоматическим навигатором |
| `test:performance` | нагрузка активной сцены и замедленный CPU |

### Арена Бойцов · `TypeScript` `Vite` `v1.0`

Командный экшен с видом сверху: 8 героев с уникальными атаками и суперударами, 3 режима, 6 карт.

- ИИ ботов: выбор цели по видимости, удержание дистанции, отступление при низком здоровье, обход препятствий, поведение под режим.
- Управление на ПК (WASD + мышь) и на телефоне (два стика, автоприцел).
- Процедурный звук и музыка на Web Audio, прогрессия, ежедневные задания, облачные сохранения, лидерборд.
- e2e-плейтест на Playwright на ПК и телефоне: все герои, все режимы до конца, сохранение; GitHub Actions.

### В разработке

Четыре игры на общем TypeScript-шаблоне с интеграцией Яндекс SDK, e2e-тестами и сборкой релиза: **Перекуп: Барахолка**, **Тряпичная Песочница**, **Полигон**, **Утащи Лут!**

## Как я работаю

- **Баг → тест → правка.** Сначала воспроизвожу проблему в тесте с замерами «до», затем исправляю и снимаю те же замеры «после».
- **Одно логическое изменение — один коммит.** Версия растёт только при видимом пользователю изменении, история ведётся в CHANGELOG.
- **AI-агенты по регламенту.** Правила работы в `AGENTS.md` / `CLAUDE.md`, журнал запусков, отчёты проверок. Каждое изменение агента проверяется автотестами.
- **Приоритеты:** сохранность данных → управление → читаемость → производительность → всё остальное.

## Сейчас изучаю

Docker и контейнеризацию, мониторинг сервисов, интеграцию LLM в продукты (API моделей, RAG).

---

<p align="center"><sub>Пишите в Telegram: <a href="https://t.me/mysoldroom">@mysoldroom</a></sub></p>
