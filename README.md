# Unity Platformer — CI/CD & Automated Testing

![Unity CI/CD](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY/workflows/CI/CD%20Pipeline/badge.svg)
![Unity Version](https://img.shields.io/badge/Unity-2022.3%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)

Проект 2D-платформера на Unity с настроенным автоматическим пайплайном CI/CD на базе GitHub Actions и game-ci, включающим автоматическое тестирование (EditMode / PlayMode) и сборку целевого билда под Windows.

---

## 📋 Особенности проекта

* Механики игрока: Движение, прыжки, двойной прыжок, приседания, получение урона, система респавна и телепортации (PlayerCharacter.cs).
* Автоматизация CI/CD: Полный цикл проверки кода при каждом push и Pull Request в ветку main.
* Тестирование: Автоматический запуск юнит- и интеграционных тестов Unity перед этапом компиляции.
* Автоматическая сборка: Генерация готовых исполняемых файлов под StandaloneWindows64 с выгрузкой в артефакты.

---

## 🛠 Техническая организация CI/CD (GitHub Actions)

Пайплайн описан в файле .github/workflows/main.yml и работает следующим образом:

### 1. Архитектура и контейнеризация
* Раннер: Виртуальная машина ubuntu-latest.
* Game-CI: Используется официальный Docker-контейнер game-ci с предустановленным окружением Unity для Linux/Windows сборок.

### 2. Этапы пайплайна (Workflow)
1. Активация и лицензирование: Используются секреты репозитория (UNITY_EMAIL, UNITY_PASSWORD, UNITY_LICENSE) для прохождения авторизации в сервисах Unity.
2. **Запуск тестов (testProject):**
 EditMode:e:** Проверка внутренней логики C#-скриптов и хелперов.
 PlayMode:e:** Симуляция работы игрового процесса, физики и взаимодействия объектов.
3. **Сборка (buildForAllDesiredPlatforms):** Компиляция ассетов и кода под StandaloneWindows64.
4. **Артефакты (upload-artifact):** Готовый заархивированный билд сохраняетсяActions **Actions** с возможностью скачивания для QA-тестирования.

---

## 🔑 Секреты репозитория (Repository Secrets)

Для корректной работы CI/CD пайплайна в настройках репозитория (Settings -> Secrets and variables -> Actions) должны быть заданы следующие переменные:

| Имя секретa | Описание |
| :--- | :--- |
| UNITY_EMAIL | Email от аккаунта Unity |
| UNITY_PASSWORD | Пароль от аккаунта Unity |
| UNITY_LICENSE | Содержимое активационного файла .ulf |

---

## 🚀 Процесс разработки и исправления багов (Git Flow)

В проекте используется регламентированный процесс обработки багов GitHub IssuesHubPull Requestsl RequПоиск бага / создание задачи:ие задачи:** Оформляется карточкIssuesе **Issues** (например, Issue #4: Персонаж теряет возможность двигаться после нескольких респавнов (смертей)).
2. **Создание ветки:** Разработчик создает локальную ветку под задачу:
   `bash
   git checkout -b fix/player-movement-bug
