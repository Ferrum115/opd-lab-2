# Отчёт по настройкам сборки и структуре проекта (build.md)

## 1. Настройки сборки (Build Settings / Build Profiles)
- **Активная платформа:** Windows (Standalone, Intel 64-bit).
- **Доступные платформы:** 
  - macOS
  - Linux
  - Windows Server / macOS Server / Linux Server
  - Android™ / iOS
  - PlayStation®4 / PlayStation®5
  - Web (WebGL)
  - Meta Quest / Android XR
  - Universal Windows Platform / tvOS / visionOS / Embedded Linux / QNXR®
- **Сцены в сборке (Scenes In Build):**
  1. `IndieMarc/PlatformerDemo/PlatformerDemo` (Индекс 0)
  2. `IndieMarc/TopDownDemo/TopDownDemo` (Индекс 1)
- **Основные настройки:**
  - **Architecture:** Intel 64-bit
  - **Build and Run on:** Local Machine
  - **Development Build:** Отключен (Release-сборка)
  - **Compression Method:** Default

---

## 2. Установленные пакеты (Package Manager)
Список пакетов Unity, установленных и используемых в проекте:

- **AI Navigation (`2.0.14`):** Инструменты для навигации и поиска пути AI (NavMesh).
- **Input System (`1.20.0`):** Новая система ввода Unity.
- **Universal Render Pipeline / Config (`17.6.0`):** Графический конвейер URP.
- **Shader Graph (`17.6.0`):** Визуальный редактор шейдеров.
- **Scriptable Render Pipeline Core (`17.6.0`):** Ядро конвейеров рендеринга.
- **Test Framework (`1.8.0`):** Фреймворк для выполнения Unit/PlayMode/EditMode тестов.
- **Timeline (`6.6.0`):** Инструмент создания кат-сцен и анимаций.
- **uGUI (`2.6.0`):** Пользовательский интерфейс Unity UI.
- **Visual Scripting (`1.9.12`):** Визуальное программирование.
- **Unity Version Control (`2.13.6`):** Интеграция с системами контроля версий (VCS/Plastic SCM).
- **Вспомогательные пакеты:** `Collections` (6.6.0), `Graph Authoring` (1.0.0), `Searcher` (4.9.5).
- **Интеграция с IDE:** `Visual Studio Editor` (2.0.26), `JetBrains Rider Editor` (3.0.38).

---

## 3. Структура папок и ассеты проекта
Структура директории `Assets/` проекта:

- **`Assets/IndieMarc/`:** Основная папка пакета Simple 2D Template.
  - **`PlatformerDemo/`:** Компоненты для режима 2D-платформера:
    - `Editor` — редакторские скрипты и расширения Unity.
    - `Materials` — 2D-материалы и физические материалы.
    - `Prefabs` — префабы игрока, платформ, опасных объектов и интерактивных элементов.
    - `Scripts` — C#-скрипты управления персонажем, прыжков, камеры и механик платформера.
    - `Sprites/` — графические ассеты (подпапки `Background`, `Character`, `Lever`).
    - `Tilemap/` — наборы тайлов для построения уровней (подпапки `Black`, `Old`).
  - **`TopDownDemo/`:** Компоненты для режима Top-Down (вид сверху):
    - `Editor`, `Materials`, `Prefabs`, `Scripts`.
    - `Sprites` и `Textures` — текстуры и спрайты персонажа, стен, дверей и ключей.
- **`Assets/Scenes`:** Игровые сцены проекта.
- **`Assets/Settings`:** Конфигурационные файлы проекта и настройки графика URP.
- **`Assets/TutorialInfo/`:** Вспомогательные скрипты, стили и иконки стартового шаблона Unity (`Editor`, `Icons`, `StyleSheets`).

---

## 4. Размер проекта и ассетов
- **Размер импортированного пакета Simple 2D Template:** 2,79 MB (175 файлов).
- **Общий размер рабочей папки проекта (включая кеш `Library/` и служебные файлы):** 2,04 ГБ (30 355 файлов, 2 797 папок).
- **Размер чистого исходного репозитория (без кеша `Library/` и `Temp/`):** ~150–250 MB.