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
## Изучить работу прецептрона на примере проекта Unity и его решения логических операций.

## Задание 1
## В проекте реализовать перцептрон, который умеет производить вычисления: OR, AND, NAND, XOR, и дать комментарии о кореектности работы.


Для начала скачиваем скрипт-файл и подключаем его к пустому объекту в проекте
![1](https://user-images.githubusercontent.com/103886479/204014445-eef66297-5198-4bc9-bba3-de3b2a91ab32.jpg)

1) Реализуем логическую операцию ИЛИ|OR

Задаём необходимые параметры

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

2) Реализуем логическую операцию Иисключающее ИЛИ|XOR

Задаём необходимые параметры

![image](https://user-images.githubusercontent.com/103886479/204080232-8a451d98-03ed-42cb-8616-2437c2e89759.png)

Сразу зададим 4 эпохи:

![image](https://user-images.githubusercontent.com/103886479/204080291-bb059192-d989-441a-82c1-16603cc392c9.png)

Результат не верный, даже спустя несколько повторений эксперимента. Меняя значения эпох обучения удалось выяснить, что с третьей-четвертой эпохи значение Total Error всегда было равно 4. Значит, однослойный перцептрон не может обучиться этой операции. XOR не является линейной операцией, соответственно однослойный прецептрон для неё не предназначен. 

Для решения применим следующий способ: воспользуемся формулой x XOR y = (x Or y) AND (x NAND y). Для этого я создала еще две модели modelOr и modelNAND.  Когда первые две модели закончили обучение, их значения были переданы в CalcOutput после тренировки модели умножения. Вот следующий скрипт:

``` 
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

[System.Serializable]
public class TrainingSet
{
	public double[] input;
	public double output;
}

public class Perceptron : MonoBehaviour {
	public TrainingSet[] modelOR;
	public TrainingSet[] modelNAND;
	public TrainingSet[] ts;
	double[] weights = {0,0};
	double bias = 0;
	double totalError = 0;

	double DotProductBias(double[] v1, double[] v2) 
	{
		if (v1 == null || v2 == null)
			return -1;
	 
		if (v1.Length != v2.Length)
			return -1;
	 
		double d = 0;
		for (int x = 0; x < v1.Length; x++)
		{
			d += v1[x] * v2[x];
		}

		d += bias;
	 
		return d;
	}

	double CalcOutput(int i, TrainingSet[] set)
	{
		double dp = DotProductBias(weights,set[i].input);
		if(dp > 0) return(1);
		return (0);
	}

	void InitialiseWeights()
	{
		for(int i = 0; i < weights.Length; i++)
		{
			weights[i] = Random.Range(-1.0f,1.0f);
		}
		bias = Random.Range(-1.0f,1.0f);
	}

	void UpdateWeights(int j, TrainingSet[] set)
	{
		double error = set[j].output - CalcOutput(j, set);
		totalError += Mathf.Abs((float)error);
		for(int i = 0; i < weights.Length; i++)
		{			
			weights[i] = weights[i] + error * set[j].input[i]; 
		}
		bias += error;
	}

	double CalcOutput(double i1, double i2)
	{
		double[] inp = new double[] {i1, i2};
		double dp = DotProductBias(weights,inp);
		if(dp > 0) return(1);
		return (0);
	}

	void Train(int epochs, TrainingSet[] set)
	{
		InitialiseWeights();
		
		for(int e = 0; e < epochs; e++)
		{
			totalError = 0;
			for(int t = 0; t < set.Length; t++)
			{
				UpdateWeights(t, set);
				Debug.Log("W1: " + (weights[0]) + " W2: " + (weights[1]) + " B: " + bias);
			}
			Debug.Log("TOTAL ERROR: " + totalError);
		}
	}

	void Start () {
		Train(8, modelOR);
		double modelOr0 = CalcOutput(0,0); //0
		double modelOr1 = CalcOutput(0,1); //1
		double modelOr2 = CalcOutput(1,0); //1
		double modelOr3 = CalcOutput(1,1); //1
		
		Train(8, modelNAND);
		double modelNAND0 = CalcOutput(0,0); //1
		double modelNAND1 = CalcOutput(0,1); //1
		double modelNAND2 = CalcOutput(1,0); //1
		double modelNAND3 = CalcOutput(1,1); //0

		Train(8, ts);
		Debug.Log("Test 0 0: " + CalcOutput(modelOr0, modelNAND0));
		Debug.Log("Test 0 1: " + CalcOutput(modelOr1, modelNAND1));
		Debug.Log("Test 1 0: " + CalcOutput(modelOr2, modelNAND2));
		Debug.Log("Test 1 1: " + CalcOutput(modelOr3, modelNAND3));		
	}
	
	void Update () {
		
	}
} 
```
После 8 тренировок я получила нужный результат эксперимента.

![xor](https://user-images.githubusercontent.com/103886479/204081084-d4929d75-b390-4d76-8a86-6515f8021b85.jpg)




## Задание 2
## Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения.
Для каждой логической операции я записала 4 попытки с 8-ю итерациями(эпохами) обучения.
Ниже вы можете видеть построенные графики с помощью программы exel.
OR:


XOR:
![image](https://user-images.githubusercontent.com/103886479/204086395-af57c2a8-3519-4969-8236-1c52d2e58d79.png)



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
