# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Чупшева Анна Романовна
- РИ210945
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |


знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)



## Цель работы
##Интеграция экономической системы в проект Unity и обучение ML-Agent

## Задание 1
Для начала запускаем проект и убеждаемся в его корректной работе. Здесь видно, как мячик передвигается из "шахты" в "город"

![запуск проекта](https://user-images.githubusercontent.com/103886479/204783152-6ff5bc33-6796-48f8-9a58-221d797e9bad.jpg)

Поместила файл Economic.yaml в проект
![yaml](https://user-images.githubusercontent.com/103886479/204790309-9b70f8ec-7fc7-44d7-bc1f-58ff0eefae9c.jpg)

Качаем библиотеки, создаём виртуальное пространство
![в отчет](https://user-images.githubusercontent.com/103886479/204814651-943bc8f5-a674-4038-944d-187d8268e2d4.jpg)

Далее была запущена сцена в Unity и обучение MLAgent. Это долгий процесс, поэтому мы увеличили количество сцен и изменили такие параметры как TargetAreaEconomic (в моем случае до 13)

![контрл с](https://user-images.githubusercontent.com/103886479/204819572-316c32c5-b6ba-4b9a-b1ed-ce19a0e2712f.jpg)

Устанавливаем и запускаем TensorBoard, видим следующее:

![graph1-1](https://user-images.githubusercontent.com/103886479/204820074-19d5518e-8fe4-452f-ac43-6bd61467adf2.jpg)

![graph1-2](https://user-images.githubusercontent.com/103886479/204820137-a390390f-e152-400c-82f4-7605e3d7b972.jpg)

## Задание 2



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
