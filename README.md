# SlimeFPS для Slime Rancher 2

Оптимизация графики и счётчик FPS как отдельный мод на **MelonLoader**. Собран из того же исходного кода, что и [Creator Toolkit](https://github.com/slitvin12/SR2-CreatorToolkit), и работает **без него**.

> *English:* SlimeFPS is a standalone MelonLoader graphics-optimization mod for Slime Rancher 2: texture quality and streaming, LOD and draw distance, decor, post-effects, runtime FPS targets, two one-click presets and an FPS counter (FPS, frame ms, per-second peak). Settings open with **F8**. It is built from the same source as Creator Toolkit but does not require it; when both are installed, Creator Toolkit automatically disables its own optimization page and FPS counter, so nothing runs twice.

**Автор:** [slitvin12](https://github.com/slitvin12) · **Версия:** 1.0.1 · Неофициальный фанатский мод, не связан с Monomi Park.

## Требования

- Slime Rancher 2 **1.3.0** (Windows).
- [MelonLoader](https://github.com/LavaGang/MelonLoader) **0.7.x** (проверено на 0.7.3).

## Установка

1. Установите MelonLoader в папку игры и один раз запустите игру.
2. Скачайте `SlimeFPS.dll` со страницы [Releases](https://github.com/slitvin12/SlimeFPS/releases/latest).
3. Положите файл в `<папка игры>\Mods\`.
4. Загрузите сохранение и нажмите **F8** — откроются настройки графики. **Esc** закрывает окно. Клавишу можно переназначить кнопкой «изменить…» в шапке окна (удобно на ноутбуках); выбор хранится в `hotkey.cfg`.

   **Если F8 не нажимается и окно не открывается:** смените клавишу без окна — откройте блокнотом `<папка игры>\UserData\SlimeFPS\hotkey.cfg` (создаётся при первом запуске) и замените `menu.key=F8` на другую клавишу, например `menu.key=Home`, затем перезапустите игру. Подойдут имена клавиш Unity: `F2`–`F12`, буквы, цифры, `Home`, `End`, `PageUp`, `PageDown`, клавиши нумпада (`Keypad0`–`Keypad9`).

Язык интерфейса следует языку игры (русский или английский). Настройки хранятся в `<папка игры>\UserData\SlimeFPS\` (выбор счётчика FPS — в `capture.cfg`).

## Возможности

- **Графика и производительность.** Четыре страницы настроек: «Текстуры и загрузка», «Дальность и декор», «Постэффекты», «Runtime FPS». Свои значения применяются кнопкой «Применить своё».
- **Пресеты.** «Сбалансированный» — мягкая оптимизация, «Максимум FPS» — максимальная. «Восстановить всё» возвращает исходные настройки игры.
- **Счётчик FPS.** FPS, мс кадра и пик за секунду в выбранном углу экрана; виден и в главном меню. Выбор сохраняется между запусками.
- **Плавная загрузка.** Единственный Harmony-хук мода сохраняет бюджет плавной загрузки после быстрой (turbo) загрузки сцен.

Настройки графики временные: «Восстановить всё», смена сейва или выход из игры возвращают исходное состояние. Мод не содержит игровых читов и не меняет сохранения.

## Совместимость с Creator Toolkit

Если рядом загружен [Creator Toolkit](https://github.com/slitvin12/SR2-CreatorToolkit), он сам отключает свою оптимизацию и счётчик FPS и показывает заметку о передаче управления на странице оптимизации. Двух счётчиков не бывает. Без Creator Toolkit SlimeFPS работает полностью самостоятельно.

## Исходный код

Разработка ведётся в монорепозитории [SR2-CreatorToolkit](https://github.com/slitvin12/SR2-CreatorToolkit): каталог `src/slimefps` (host-класс и окно настроек) линкует общий код `src/creator` без изменений. Сборка — из корня того репозитория после подготовки `refs/` и локального .NET SDK (инструкция в его README):

```powershell
.\_work\dotnet\dotnet.exe build src\slimefps\SlimeFPS.csproj -c Release
```

## Проверено

Сборка: 0 предупреждений / 0 ошибок (net6.0). Офлайн-проверки общего кода: **5068 PASS**. Проверено в живой игре (2026-11-11): окно настроек открывается, клавиша меню переназначается кнопкой «изменить…» в шапке и через `hotkey.cfg`, 0 ошибок в логе. Совместная работа с Creator Toolkit и SlimeMap проверена 2026-11-10: один счётчик FPS.

## Лицензия

Код мода распространяется по лицензии [MIT](LICENSE). Сторонние материалы под неё не подпадают (подробно — [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)): Slime Rancher 2, её названия и графика принадлежат Monomi Park; значки и часть меток взяты с Fandom-вики ([CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)).