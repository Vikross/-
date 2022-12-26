# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по проекту выполнил(а):
- Емелькина Виктория Евгеньевна
- РИ210947

## Цель работы
Объединить все полученные на курсе знания в один проект.
## Цель проекта
Данный проект можно интергировать в приложения, где нужны операции с экономикой.

## Ход работы:

1. Создала куб и сферу.

2. С помощью ML-агента обучила сферу передвигаться от своего места к кубу.

3. Использовала перцептрон, установила значения.

4.  Исходя из значений в перцептроне куб менял цвет при столкновении со сферой:
  0 0 - куб становится красным и звучит сигнал
  1 0 или 0 1 или 1 1 - куб становится зеленым и звучит сигнал
  
![image](https://user-images.githubusercontent.com/94571271/209584361-37b38692-9800-43ee-ae57-a05b602d5fbc.png)


![image](https://user-images.githubusercontent.com/94571271/209584372-410a5fe1-1181-47bc-8676-320645914ccd.png)

Код на изменение цвета куба:
```py

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ChangeColor : MonoBehaviour
{
    static double value = 0;

    public void OnTriggerEnter(Collider other)
    {
        if (value == 0)
            this.gameObject.GetComponent<Renderer>().material.color = Color.red;
        else
            this.gameObject.GetComponent<Renderer>().material.color = Color.green;
    }

    public static void OnSearchValue(double answer)
    {
        value = answer;
    }
}


