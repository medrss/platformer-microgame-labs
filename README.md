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
