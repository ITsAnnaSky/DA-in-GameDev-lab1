# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
- Чупшева Анна Романовна
- РИ210945
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)



## Цель работы
Изучить работу прецептрона на примере проекта Unity и его решения логических операций.

## Задание 1
В проекте реализовать перцептрон, который умеет производить вычисления: OR, AND, NAND, XOR, и дать комментарии о кореектности работы.


Для начала скачиваем скрипт-файл и подключаем его к пустому объекту в проекте
![1](https://user-images.githubusercontent.com/103886479/204014445-eef66297-5198-4bc9-bba3-de3b2a91ab32.jpg)

1) Реализуем логическую операцию ИЛИ|OR

![3](https://user-images.githubusercontent.com/103886479/204014692-a9552452-2d3f-41ce-a846-ac7b3ffdd1b0.jpg)

Зададим 1 эпоху как в леции и понаблюдаем за тестами в консоли:
![И 1 эпоха](https://user-images.githubusercontent.com/103886479/204076192-1b8ff989-6939-43c9-b2ce-2bb9e46eb33b.jpg)

Как мы видим, значение TotalError != 0, хотя должно быть ноль. Это значит, что наш прецептрон не обучился должным образом. Та же ситуация происходит и с 2-мя эпохами обучения.   

Задаём 6 эпох

![image](https://user-images.githubusercontent.com/103886479/204076602-286293bb-9045-4d9e-8646-c2e4f5ff97fe.png)

В конечном итоге мы получили значение TotalError = 0, что говорит об успешном обучении прецептрона. 

Если же дать прецептрону значения на вход и поставить 4 эпохи обучения, то мы также получим верный результат

![image](https://user-images.githubusercontent.com/103886479/204076750-6d2fb0a6-4918-40f3-a840-2ef49573aa21.png)


2) Реализуем логическую операцию И|AND

Задаём необходимые параметры
![image](https://user-images.githubusercontent.com/103886479/204020593-ae20819d-80e5-460b-9a02-829354130910.png)

Зададим 1 эпоху для прецептрона и посмотрим на результаты тестов

![image](https://user-images.githubusercontent.com/103886479/204078670-17d79578-ed09-44ce-bd60-d12fd06c9fcd.png)

Как и ожидалось, одной эпохи не достаточно для корректного результата

Зададим 4 эпохи

![image](https://user-images.githubusercontent.com/103886479/204078814-ff5ea022-16b6-4362-bb76-5304f1daae8d.png)
![image](https://user-images.githubusercontent.com/103886479/204078830-37578699-1ce4-4a77-830a-8bac333e849c.png)

Результат некорректен. Я повторила эксперимент несколько 4-5 раз и не получила корректного результата. 

Зададим 5 эпох

![image](https://user-images.githubusercontent.com/103886479/204079063-d3d6ab86-89f9-49af-a02d-0bf443f2f8d5.png)
![image](https://user-images.githubusercontent.com/103886479/204079076-16473ea4-effd-4474-b276-df8b4bbaa2b7.png)

Здесь для получения верного ответа мне потребовалось повторить эксперимент 3 раза.

3)Реализуем логическую операцию НЕ И|NAND

Задаём необходимые параметры
![image](https://user-images.githubusercontent.com/103886479/204079397-c583e74d-ab67-4764-bf61-fd298ec97338.png)


Зададим 1 эпоху для прецептрона и посмотрим на результаты тестов

![image](https://user-images.githubusercontent.com/103886479/204079219-33ff6008-9f31-4f83-a673-b2d3068a44f2.png)

Нет корректного ответа

Зададим 4 эпохи
![image](https://user-images.githubusercontent.com/103886479/204079302-6945eade-1245-4890-83c2-460ebbf9cf28.png)
![image](https://user-images.githubusercontent.com/103886479/204079315-7eb29d2c-15ed-4cf3-a51f-7f36d7b134e8.png)

Нет корректного ответа. Однако, с 3-го раза дал следующие результаты

![image](https://user-images.githubusercontent.com/103886479/204079446-8625eec7-88bb-469f-99db-03c32e6b9fb8.png)

Я решила увеличить колиество эпох обучения до 8 и, спустя несколько запусков, получила верный ответ

![image](https://user-images.githubusercontent.com/103886479/204079576-10d74049-92c7-4f52-adaf-dfd9c9dee429.png)
![image](https://user-images.githubusercontent.com/103886479/204079592-a747dab8-9a33-4522-8dac-36148b3fd407.png)

2) Реализуем логическую операцию И|AND


## Задание 2



## Задание 3

## Выводы

В данной лабораторной работе мы настроили всё необходимое ПО для дальнейшей работы и теперь имеем представление, как пользоваться VS Code, и Unity. Узнали что такое градиентный спуск, линейная зависимость, алгоритм градиентного спуска. Научились использовать GoogleColab и Github. 

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
