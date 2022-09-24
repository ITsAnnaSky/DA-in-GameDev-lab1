# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Чупшева Анна Романовна
- РИ210945
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

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
На данном скриншоте использован GoogleColab для демонстрации работы кода на  pyhton.

![helloWorld](https://user-images.githubusercontent.com/103886479/192082146-32e09368-f568-444a-9722-ce98476ea996.jpg)

На следующих двух скриншотах представлен код на языке C#, в программе Unity. В процессе выполнения работы обратила внимание на то, что для выполнения кода необходима его привязка к какому-либо объекту.

![helloworld1](https://user-images.githubusercontent.com/103886479/192082931-94c2c772-1f14-43ea-b740-d4c9b55c38ee.jpg)
![DONE](https://user-images.githubusercontent.com/103886479/192082941-83502152-8052-4ce7-b918-275ea4ade4ae.jpg)

## Задание 2
Подготовка данных для работы с линейной регрессией:

![подготовка](https://user-images.githubusercontent.com/103886479/192092265-952fbf33-f5b0-417d-81b2-8eab763d0245.jpg)


Далее смотрим на функции:

![функции](https://user-images.githubusercontent.com/103886479/192092316-e3934b65-e292-4ac8-8f9f-09012910d14c.jpg)

   
   Насколько я понимаю, связанными функциями называются iterate и optimize. optimize и выполняет градиентный спуск, т.е. метод нахождения минимума функции. Это нам понадобится для построения линейной регрессии.
   
   
После запуска первой итерации в GoogleColab получилось следующее:
![код11](https://user-images.githubusercontent.com/103886479/192091115-14e1e329-bf0e-433d-b65c-701274efb3ae.jpg)

Второй итерации:
![код2](https://user-images.githubusercontent.com/103886479/192090736-f63f7562-25c2-4d48-9bc5-7f04f4ebe418.jpg)

Третьей:
![код3](https://user-images.githubusercontent.com/103886479/192090824-06a29e31-4b97-4a1c-9a39-913d54e9f7b0.jpg)

Четвёртой:
![код4](https://user-images.githubusercontent.com/103886479/192090920-8990a2dd-18aa-4615-8a3e-f6e20e9b572a.jpg)

Пятой:
![код5](https://user-images.githubusercontent.com/103886479/192090958-da529913-9295-4915-b05f-ceab3f35b4de.jpg)

Тысячной:
![код1000](https://user-images.githubusercontent.com/103886479/192091219-6a2ce8d0-6d30-4c87-8c71-52a5326128b8.jpg)

Как мы видим, чем больше итераций, тем выше график.

### Должна ли величина loss стремиться к нулю при изменении исходных данных? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ.

Полагаю, да. loss - это величина, которая показывает количество потерь. По мере увеличения нами количества итераций мы наблюдаем уменьшение этой величины.

Пример: 
1 итерация
![код11](https://user-images.githubusercontent.com/103886479/192091115-14e1e329-bf0e-433d-b65c-701274efb3ae.jpg)

10-я итерация
![10](https://user-images.githubusercontent.com/103886479/192091791-bb13b7d8-db2f-4fff-85c4-1a4e72deed32.jpg)

100-я итерация
![100](https://user-images.githubusercontent.com/103886479/192091680-8751f16f-1acc-40d7-a5f8-4b8dc97a727b.jpg)

1000-я
![код1000](https://user-images.githubusercontent.com/103886479/192091219-6a2ce8d0-6d30-4c87-8c71-52a5326128b8.jpg)

10000-я
![10000](https://user-images.githubusercontent.com/103886479/192091837-aa53f09d-2bcc-421b-a237-7a3cd871162a.jpg)


## Задание 3
### Какова роль параметра Lr? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ. В качестве эксперимента можете изменить значение параметра.
Lr, если я правильно понимаю, - это параметр скорости обучения, необходимый для алгоритма градиентного спуска. 


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
