# Лабораторная работа №1: Автоматизация сборки 2D игры через CLI

**Студентка:** Карелина Мария Дмитриевна

**Группа:** 23-СТ

## Цель работы
Освоить сборку Unity-проекта через командную строку (CLI) и интеграцию процесса в Git/GitHub.

## 1. Создание проекта
Создан новый проект на базе шаблона 2D Platformer Microgame.

## 2. Скрипт BuildManager.cs
Написан C# скрипт для автоматической сборки WebGL-версии игры.

<img width="1920" height="1031" alt="image" src="https://github.com/user-attachments/assets/48a56f53-9f47-4b10-a324-bb09e5ef02e6" />

## 3. Настройка WebGL
В настройках Player → Publishing Settings установлен Compression Format = Disabled.

## 4. Сборка через CLI
Запущена команда:
```
"D:\Programs\Unity\Hub\Editor\6000.5.10f1\Editor\Unity.exe" -batchmode -nographics -executeMethod BuildManager.BuildWebGL -quit -logFile build_webgl.log
```

В логе: `[CI/CD] УСПЕХ! WebGL билд успешно создан.`

<img width="646" height="348" alt="image" src="https://github.com/user-attachments/assets/5132176e-e971-44d0-89ad-5e7edd2151bc" />

## 5. Проверка через Live Server
Игра успешно запущена в браузере по адресу `http://127.0.0.1:5500`.

<img width="646" height="326" alt="image" src="https://github.com/user-attachments/assets/334b4959-52c7-48e2-87b2-f22528415912" />

## Вывод
В ходе работы освоена автоматизация сборки Unity-проекта через CLI, интеграция процесса в Git с использованием веток и Pull Request.

# Лабораторная работа №2: Настройка GitHub Actions и автоматическая проверка проекта

## Цель работы

Изучить принципы построения сценариев непрерывной интеграции (CI) на платформе GitHub Actions, настроить автоматическую проверку структуры Unity-проекта и автоматическое зеркалирование репозитория в резервную копию.

## 1. Создание резервного репозитория

Создан отдельный резервный репозиторий `2d_platformer_backup` для автоматического копирования исходного кода и истории коммитов основного проекта.

## 2. Настройка токена доступа

Создан Personal Access Token (PAT) с необходимыми разрешениями для работы с репозиториями. Токен сохранён в разделе Secrets основного репозитория под именем `BACKUP_TOKEN`.

<img width="646" height="299" alt="image" src="https://github.com/user-attachments/assets/1325d84e-cb8f-4855-8506-6d9884877507" />

## 3. Создание YAML-пайплайна

Создан файл `.github/workflows/main.yml`, содержащий две задачи:

* `sanity_check` — проверка наличия основных директорий Unity-проекта и поиск C#-скриптов.
* `mirror_repo` — автоматическое зеркалирование репозитория в резервный репозиторий после успешного завершения проверки.

<img width="646" height="343" alt="image" src="https://github.com/user-attachments/assets/3caf4efe-9bcc-496f-970a-c9c1c93e874c" />

## 4. Интеграция с GitHub

Создана ветка `LR2`, изменения отправлены в GitHub и объединены с веткой `main` с помощью Pull Request.

<img width="646" height="299" alt="image" src="https://github.com/user-attachments/assets/fd881a8e-5348-47f6-af4f-c77fecaf22f5" />

## 5. Проверка GitHub Actions

Во вкладке Actions проверен результат выполнения автоматического рабочего процесса. Проверка структуры проекта и задача зеркалирования должны завершаться успешно.

## 6. Проверка резервного репозитория

Проверено наличие файлов проекта в резервном репозитории после выполнения автоматического зеркалирования.

<img width="646" height="298" alt="image" src="https://github.com/user-attachments/assets/ac2f499c-67e5-4dd5-8b15-0a552d2a8c7f" />

## Вывод

В ходе лабораторной работы изучены основы настройки GitHub Actions. Создан YAML-пайплайн для автоматической проверки структуры Unity-проекта и зеркалирования репозитория. Настроено безопасное хранение токена доступа в GitHub Secrets и проверена работа автоматизированного процесса.

