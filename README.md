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

## Настройки по умолчанию
![graph1-1](https://user-images.githubusercontent.com/103886479/204820074-19d5518e-8fe4-452f-ac43-6bd61467adf2.jpg)


![graph1-2](https://user-images.githubusercontent.com/103886479/204820137-a390390f-e152-400c-82f4-7605e3d7b972.jpg)


![policy-1](https://user-images.githubusercontent.com/103886479/204821032-bfc0e593-886b-4ceb-bcd4-220dae5b8fd6.jpg)
![policy-2](https://user-images.githubusercontent.com/103886479/204821054-f52859df-f481-4227-8f88-467922049b18.jpg)
![policy-3](https://user-images.githubusercontent.com/103886479/204821094-41458554-241f-4a19-95ec-c7d84f015f44.jpg)


![self-play](https://user-images.githubusercontent.com/103886479/204821127-f335b010-ea54-4880-b130-78f87c561bca.jpg)

## с buffer_size: 13000

![newgraph-1](https://user-images.githubusercontent.com/103886479/204825987-4dcbaacc-e3c9-4a9b-9749-c877f106c232.jpg)
![newgraph-2](https://user-images.githubusercontent.com/103886479/204826027-7ba4e86e-0065-47ba-bfec-f51f7cb65c00.jpg)
![newgraph-3](https://user-images.githubusercontent.com/103886479/204826108-3c68d1e7-86ec-4493-a794-7303e1899b90.jpg)
![newgraph-4](https://user-images.githubusercontent.com/103886479/204826134-3f26873f-7cd1-46da-9693-68189a92b435.jpg)
![newgraph-5](https://user-images.githubusercontent.com/103886479/204826155-d3ed14e6-78cd-46c6-a29b-d6087fe4b592.jpg)
![newrhaph-6](https://user-images.githubusercontent.com/103886479/204826190-e9b71655-c7d5-49d7-89c5-38f176737a1a.jpg)

## Задание 2

Смотря на графики, можно сделать соответствующие выводы:
Если график Cumulative Reward идёт вверх, знаит обучение можно считать удавшимся. При настройках по умолчанию hidden_units и num_layers MLAgent обучается медленно, поэтому их следует увеличить. Ну и при порядком увеличенном buffer_size графики начинают показывать странные результаты. Как я предполагаю, в MLAgent просто перегружается, значит в этом значении нужно соблюдать баланс.

## Выводы

В данной лабораторной работе мы обучали MLAgent-а, сохранять определённые темпы инфляции. Проводили обучения, изменяли параметры и фиксировали данные на графиках, после чего проанализировали получившиеся результаты.

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
