# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #3 выполнил(а):
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
Познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity.

## Задание 1

Для начала мы в Unity добавим все нужные библиотеки:

ml-agents-release_19/com.unity.ml-agents/package.json
ml-agents-release_19/com.unity.ml-agents.extensions/package.json

![задание 1](https://user-images.githubusercontent.com/103886479/198079908-4f1f4bff-d173-4ea2-829f-586ed8b3892a.jpg)

Далее активируем MLAgent

![1222](https://user-images.githubusercontent.com/103886479/198081770-8ecd0b79-b116-4b93-943b-3f05aaa3c99d.jpg)

Затем создаём объекты, которые в дальнейшем предстоит обучить 

![1 3](https://user-images.githubusercontent.com/103886479/198081910-d5820a36-7f4e-4b86-8ed5-28cdce1abfa7.jpg)

После этого мы добавляем скрипт для шара:

using System.Collections;

using System.Collections.Generic;

using UnityEngine;

using Unity.MLAgents;

using Unity.MLAgents.Sensors;

using Unity.MLAgents.Actuators;

public class RollerAgent : Agent
{
    Rigidbody rBody;
    void Start()
    {
        rBody = GetComponent<Rigidbody>();
    }
    public Transform Target;
    public override void OnEpisodeBegin()
    {
        if (this.transform.localPosition.y < 0)
        {
            this.rBody.angularVelocity = Vector3.zero;
            this.rBody.velocity = Vector3.zero;
            this.transform.localPosition = new Vector3(0, 0.5f, 0);
        }
        Target.localPosition = new Vector3(Random.value * 8-4, 0.5f, Random.value * 8-4);
    }
    public override void CollectObservations(VectorSensor sensor)
    {
        sensor.AddObservation(Target.localPosition);
        sensor.AddObservation(this.transform.localPosition);
        sensor.AddObservation(rBody.velocity.x);
        sensor.AddObservation(rBody.velocity.z);
    }
    public float forceMultiplier = 10;
    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        Vector3 controlSignal = Vector3.zero;
        controlSignal.x = actionBuffers.ContinuousActions[0];
        controlSignal.z = actionBuffers.ContinuousActions[1];
        rBody.AddForce(controlSignal * forceMultiplier);
        float distanceToTarget = Vector3.Distance(this.transform.localPosition, Target.localPosition);
        if(distanceToTarget < 1.42f)
        {
            SetReward(1.0f);
            EndEpisode();
        }
        else if (this.transform.localPosition.y < 0)
        {
            EndEpisode();
        }
    }
}


Добавление Decision Requester и Behavior Parameters

![1 4](https://user-images.githubusercontent.com/103886479/198086697-29529708-09ed-40ed-94d7-7c4a5fc311e8.jpg)

Далее следовало запустить обучение сначала на одной площадке:
(шар и куб раскрасила)

![обучение](https://user-images.githubusercontent.com/103886479/198087321-cbd20224-8b0a-40b0-ac5b-44ecedadcddd.jpg)

![обучение2](https://user-images.githubusercontent.com/103886479/198087634-94f17e11-456a-4edb-af6e-4e7a4a4a7459.jpg)

Затем на нескольких. Их количество нужно увеличивать

![3 площадки](https://user-images.githubusercontent.com/103886479/198087853-e6f11eee-5b85-499e-a9ef-6207ea3e81e9.jpg)

![9 площадок](https://user-images.githubusercontent.com/103886479/198088294-e231779b-c54b-4b7f-866a-d1e2e220ced9.jpg)

Далее следует остановить остановить работу по достижении большого кол-ва шагов и проверить обучение

![конец](https://user-images.githubusercontent.com/103886479/198088614-127ad56a-d2be-4576-a4e2-6ffc010b0bf5.jpg)

Соответственно, делаем вывод, что чем больше площадок используется, тем большее количество шагов осуществляется и обучение происходит в более быстром темпе.


## Задание 2
Подробно описать каждую строку файла конфигурации нейронной сети. Самостоятельно найти информацию о компонентах Decision Requester, Behavior Parameters, добавленных сфере.

trainer_type - тип обучения
                                                    
hyperparameters - параметры для управления обучением
                                                    
    batch_size - количество опыта на каждом шаге
                                                    
    buffer_size - сколько опыта нужно для обновления модели
    learning_rate - начальная скорость обучения
    beta - случайные действия агента
    epsilon - ограничение на изменения в модели
    lambd - регуляция, как сильно агент полагается на текущий value estimate
    num_epoch - столько раз обрабатываем опыт
    learning_rate_schedule - скорость обучения с течением времени
network_settings - параметры нейронной сети
    normalize - применяем ли нормализация к наблюдаемым данным да/нет
    hidden_units - количество нейронов сети
    num_layers - количество скрытых слоёв в нейронной сети
reward_signals - награда за действие агента
    extrinsic - внешние сигналы
        gamma - получит ли агент награду сейчас
        strength - умножает награду полученную от окружения
max_steps - сколько должно быть шагов перед завершением обучения
time_horizon - необходимое агенту кол-во опыта, чтобы добавить его в buffer_size
summary_freq - количество опыта, для выведения статистики





## Выводы
В данной лабораторной работе мы наглядно увидели, как работает внутриигровой баланс. Продуманность и качество разработанной игры показывает её сбалансированность. Если в игру слишком сложно играть - у пользователя опустятся руки, а если игра слишком лёгкая, заниматься ей просто неинтересно. Для соблюдения этого балланса расзработчикам приходит на помощь машинное обучение, которое позволяет продумать и скорректировать поведение игровых персонажей/объектов под конкретного ирока. 


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
