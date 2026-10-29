<p align="right"><b>ru</b> / <a href="https://github.com/commeu/commeu/blob/main/README.en.md">en</a></p>

<picture><source media="(max-width: 700px)" srcset="assets/v3/hero-ru-m.svg"><img src="assets/v3/hero-ru.svg" alt="comm eu: разработка, браузерные игры, автоматизация и сети" width="100%"></picture>

<p align="center">
comm eu пишет код, настраивает сети и собирает игры для браузера.<br>
полтора года в it: сети и оборудование, скрипты, свой софт и его автоматизация.<br>
веду команду из 7+ человек и работаю с клиентами напрямую.
</p>

<p align="center">
<a href="#objects">объекты²</a> &nbsp;/&nbsp; <a href="#chronicle">хроника³</a> &nbsp;/&nbsp; <a href="#method">метод⁴</a> &nbsp;/&nbsp; <a href="#stack">состав⁵</a> &nbsp;/&nbsp; <a href="#signal">связь⁶</a>
</p>

<details>
<summary><b>навигатор:</b> что смотреть под вашу роль</summary>
<br>

| роль | раздел | что там |
|---|---|---|
| фронтенд, веб | <a href="#objects">2.1</a>, <a href="#stack">5</a> | canvas без движков и зависимостей, 28 раскладок экрана, сборка в один html |
| геймдев | <a href="#objects">2.1</a>, <a href="#objects">2.2</a>, <a href="#chronicle">3</a> | две готовые игры, ещё четыре на общем шаблоне, 33 релиза за 13 дней |
| qa, автотесты | <a href="#objects">2.1</a>, <a href="#method">4</a> | 6 наборов тестов на node и playwright, тест до правки, e2e на пк и телефоне |
| devops, инфраструктура | <a href="#objects">2.3</a>, <a href="#objects">2.1</a> | сети и оборудование, автоматизация, ci в github actions с артефактами |
| тимлид, менеджер | <a href="#objects">2.3</a>, <a href="#method">4</a>, <a href="#chronicle">3</a> | команда 7+ человек, работа с клиентами, разработка с агентами по регламенту |

</details>

<a id="objects"></a>
<picture><source media="(max-width: 700px)" srcset="assets/v3/band-objects-ru-m.svg"><img src="assets/v3/band-objects-ru.svg" alt="2 объекты" width="100%"></picture>

<picture><source media="(max-width: 700px)" srcset="assets/v3/group-release-ru-m.svg"><img src="assets/v3/group-release-ru.svg" alt="2.1 игры, к релизу" width="100%"></picture>

<picture><source media="(max-width: 700px)" srcset="assets/v3/fox-raid-ru-m.svg"><img src="assets/v3/fox-raid-ru.svg" alt="Лисий рейд: стелс-аркада на javascript и canvas, 6 наборов автотестов" width="100%"></picture>

<details>
<summary><b>Лисий рейд:</b> тесты, платформа, устройство проекта</summary>
<br>

| набор тестов | что проверяет |
|---|---|
| `npm test` | механика, сохранения, качество графики, первые 20 контрактов |
| `test:browser` | управление, сценарии sdk, восстановление аккаунта, доступность (playwright) |
| `codex:release` | собранные html и zip: настоящий ввод, перезагрузка, нет тестового кода |
| `test:local-layouts` | 28 сочетаний ru/en и 7 размеров экрана, крупный текст и контраст |
| `test:progression` | непрерывное прохождение всех зон и коллекции автоматическим навигатором |
| `test:performance` | нагрузка активной сцены и замедленный процессор |

**платформа:** облачные сохранения по постоянному id игрока, пауза при сворачивании, реклама за награду только по желанию игрока, game ready и gameplay api яндекса. sdk в тестах заменён моками, реальные устройства и реклама проверяются в черновике платформы.

```
game/      исходники: ядро, платформа, графика, качество, анимация
tests/     node- и playwright-тесты (50 файлов)
scripts/   сборка пакета, медиа, диагностика
docs/      состояние, отчёты, доказательства проверок
media/     скриншоты и кадры «до/после»
```

</details>

<picture><source media="(max-width: 700px)" srcset="assets/v3/arena-ru-m.svg"><img src="assets/v3/arena-ru.svg" alt="Арена Бойцов: командный экшен на typescript и vite" width="100%"></picture>

<details>
<summary><b>Арена Бойцов:</b> конвейер сборки и устройство проекта</summary>
<br>

каждый push в main проходит в github actions:

1. проверка типов typescript
2. сборка
3. zip для платформы
4. e2e-плейтест в chromium: все 8 героев, три режима до конца, путь кубков, прокачка, сохранение
5. скриншоты плейтеста и архив игры сохраняются артефактами

```
src/game/heroes.ts    8 героев: характеристики, суперы, пассивки, цены прокачки
src/game/maps.ts      6 зеркальных карт и режимы
src/game/arena.ts     симуляция боя и ии ботов
src/game/progress.ts  сохранение, путь кубков, задания
src/render/draw.ts    отрисовка арены с кешем слоёв карты
src/audio/sfx.ts      процедурный звук и музыка
tests/e2e.cjs         плейтест на playwright
```

</details>

<picture><source media="(max-width: 700px)" srcset="assets/v3/group-wip-ru-m.svg"><img src="assets/v3/group-wip-ru.svg" alt="2.2 игры, в разработке" width="100%"></picture>

| игра | жанр | основа |
|---|---|---|
| Перекуп: Барахолка | тайкун | typescript, яндекс sdk, e2e-тесты |
| Тряпичная Песочница | физическая песочница | typescript, яндекс sdk, e2e-тесты |
| Полигон | физический шутер-полигон | typescript, яндекс sdk, e2e-тесты |
| Утащи Лут! | обби | typescript, яндекс sdk, e2e-тесты |

<picture><source media="(max-width: 700px)" srcset="assets/v3/group-infra-ru-m.svg"><img src="assets/v3/group-infra-ru.svg" alt="2.3 инфраструктура и автоматизация" width="100%"></picture>

<p>
┌<br>
на текущей работе: настройка сетей и сетевого оборудования,<br>
скрипты и собственный софт, автоматизация их запуска и проверок.<br>
руковожу командой из 7+ человек, сам веду клиентов от требований до сдачи.<br>
└
</p>

<a id="chronicle"></a>
<picture><source media="(max-width: 700px)" srcset="assets/v3/band-chronicle-ru-m.svg"><img src="assets/v3/band-chronicle-ru.svg" alt="3 хроника" width="100%"></picture>

<picture><source media="(max-width: 700px)" srcset="assets/v3/chronicle-ru-m.svg"><img src="assets/v3/chronicle-ru.svg" alt="33 релиза Лисьего рейда за 13 дней: 9, 10, 12 и 21 октября 2026, из них 15 новых механик за 21 октября" width="100%"></picture>

<a id="method"></a>
<picture><source media="(max-width: 700px)" srcset="assets/v3/band-method-ru-m.svg"><img src="assets/v3/band-method-ru.svg" alt="4 метод" width="100%"></picture>

<picture><source media="(max-width: 700px)" srcset="assets/v3/method-ru-m.svg"><img src="assets/v3/method-ru.svg" alt="баг: сначала тест; коммит: одно изменение; агенты: по правилам и через тесты; порядок: данные игрока, управление, читаемость, скорость" width="100%"></picture>

<a id="stack"></a>
<picture><source media="(max-width: 700px)" srcset="assets/v3/band-stack-ru-m.svg"><img src="assets/v3/band-stack-ru.svg" alt="5 состав" width="100%"></picture>

<picture><source media="(max-width: 700px)" srcset="assets/v3/tag-ru-m.svg"><img src="assets/v3/tag-ru.svg" alt="состав: typescript, javascript, python, canvas, web audio, vite, node.js, playwright, github actions, git, сети, claude code, openai codex; изучаю docker, мониторинг, llm и rag" width="100%"></picture>

<details>
<summary><b>указатель:</b> технология → где применяется</summary>
<br>

| технология | где |
|---|---|
| javascript | Лисий рейд: вся игра без движка |
| typescript | Арена Бойцов и четыре игры в разработке |
| canvas | отрисовка обеих готовых игр |
| web audio | процедурный звук и музыка Арены |
| vite | сборка и dev-сервер Арены |
| node.js | тесты Лисьего рейда, скрипты сборки |
| python | сборка пакета Лисьего рейда для платформы |
| playwright | e2e-тесты обеих игр на пк и телефоне |
| github actions | ci Арены: типы, сборка, плейтест, артефакты |
| яндекс sdk | облачные сохранения, реклама, лидерборды, game ready |
| claude code, codex | разработка агентами по письменному регламенту |
| сети | текущая работа: сети и сетевое оборудование |

</details>

<a id="signal"></a>
<picture><source media="(max-width: 700px)" srcset="assets/v3/band-signal-ru-m.svg"><img src="assets/v3/band-signal-ru.svg" alt="6 связь" width="100%"></picture>

<a href="https://t.me/mysoldroom"><picture><source media="(max-width: 700px)" srcset="assets/v3/signal-ru-m.svg"><img src="assets/v3/signal-ru.svg" alt="написать в telegram @mysoldroom" width="100%"></picture></a>

<picture><source media="(max-width: 700px)" srcset="assets/v3/footer-ru-m.svg"><img src="assets/v3/footer-ru.svg" alt="comm eu" width="100%"></picture>
