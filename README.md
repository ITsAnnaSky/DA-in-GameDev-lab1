# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Чупшева Анна Романовна
- РИ210945
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | # | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)



## Цель работы
Ознакомиться с основными операторами зыка Python на примере реализации линейной регрессии.

## Задание 1
### Пошагово выполнить каждый пункт раздела "ход работы" с описанием и примерами реализации задач
С помощью видео-инструкции я настроила вывод чисел в таблицу с помощью проекта PyCharm
![скрин 1 1](https://user-images.githubusercontent.com/103886479/194914921-052b81c7-0cae-4a83-8265-083678e13ae5.jpg)
![скрин 1 2](https://user-images.githubusercontent.com/103886479/194914950-fb5e6d78-8167-4c82-8fce-b7566ef04fef.jpg)
![скрин 1 3](https://user-images.githubusercontent.com/103886479/194915429-7ec3285a-d3c2-46d5-a268-fca78f3f8176.jpg)

Далее я подготовила проект на Unity, воспроизводящий звуки
![скрин 1 5](https://user-images.githubusercontent.com/103886479/194918136-8d8e877e-a54b-463a-9a12-a77d09617667.jpg)


## Задание 2
Реализовать запись в Google-таблицу набора данных, полученных с помощью линейной регрессии из лабораторной работы № 1

Скриншот из гугл-таблицы:
![скрин 1 6](https://user-images.githubusercontent.com/103886479/194922918-99d1495d-d49e-4528-a4a5-9262d3ff52af.jpg)

Данный код возвращает данные в гугл-таблицу данные с прошлой лабораторной работы:

import gspread
import numpy as np


def loss_function(a, b, x, y):
    num = len(x)
    prediction = model(a, b, x)
    return (0.5 / num) * (np.square(prediction - y)).sum()

def model(a, b, x):
    return a * x + b

def optimize(a, b, x, y):
    num = len(x)
    prediction = model(a, b, x)

    da = (1.0 / num) * ((prediction - y) * x).sum()
    db = (1.0 / num) * ((prediction - y).sum())
    a = a - Lr * da
    b = b - Lr * db
    return a, b

def iterate(a,b,x,y,times):
    for i in range(times):
        a,b = optimize(a,b,x,y)
    return a,b

gc = gspread.service_account(filename='unitydatasciense-364505-581a2046f5a2.json')
sh = gc.open('UnitySheet')
x = [3, 21, 22, 34, 54, 34, 55, 67, 89, 99]
x = np.array(x)
y = [2, 22, 24, 65, 79, 82, 55, 130, 150, 199]
y = np.array(y)
a = np.random.rand(1)
b = np.random.rand(1)
Lr = 0.0001
print(a,b,loss)
i = 0
while i <= len(x+1):
    i += 1
    if i == 0:
        continue
    else:
        iter = np.random.randint(1, 15)
        print(iter)
        a,b = iterate(a,b,x,y,iter)
        loss = loss_function(a, b, x, y)
        tempInf = loss
        tempInf = str(tempInf)
        tempInf = tempInf.replace('.', ',')
        sh.sheet1.update(('A' + str(i)), str(x[i-1]))
        sh.sheet1.update(('B' + str(i)), str(y[i-1]))
        sh.sheet1.update(('C' + str(i)), str(tempInf))
        print(tempInf)


## Выводы

Мы научились пользоваться GoogleCloud, подключили проект в PyCharm к таблицам, научились адаптировать код для разных задач.

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
