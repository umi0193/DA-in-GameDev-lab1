# Лабораторная работа 1. Основы работы в среде разработки игр и интерактивных приложений. Основы работы c Unity.
Отчет по лабораторной работе #1 выполнила:
- Стрельчук Анастасия Александровна
- 1948616

Отметка о выполнении заданий:

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |


Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Подготовка среды
- Задание 1.
- В разделе «ход работы» пошагово выполнить каждый пункт с описанием и
примера реализации задач по теме видео «Практическая работа 1-4».
- Задание 2.
Продемонстрировать на сцене в Unity следующее:
 1) Что произойдёт с координатами объекта, если он перестанет быть
дочерним?
 2) Создать три различных примера работы компонента RigidBody.
- Задание 3.
Реализовать на сцене генерацию n кубиков. Число n вводится
пользователем после старта сцены.
- Выводы.

## Цель работы
ознакомиться с основными функциями Unity и взаимодействием с объектами внутри редактора.

## Подготовка среды
Для выполнения первой и последующих лабораторных работ я произвела:
- авторизацию на сайте Unity ID
- скачивание и установку Unity Hub
- скачивание и установку VS Code и два доп. пакета, а именно: .NET Framework 4.8 Developer Pack и .NET 6 SDK
- установку редактора Unity и расширения на VS Code: Unity Tools и Unity Code Snippets, C# и C# XML Documentation
- создание первого проекта на Unity (3D) и интегрирование туда VS Code. 


## Задание 1
### В разделе «ход работы» пошагово выполнить каждый пункт с описанием и примера реализации задач по теме видео «Практическая работа 1-4».
Ход работы:
1) Открыла созданный при подготовке среды проект
2) Проверила интеграцию VS Code
3) Познакомилась с рабочими областями (окно иерархии, окно инспектора, окно Assets)
4) Создала следующие обьекты, кликнув правой кнопкой мыши на окно иерархии, далее 3D objects, выбрав из списка: plane, cube и sphere
5) Удобно разместила в пространстве объекты
6) Для идентификации обьектом sphere его столкновения с другими обьектами в характеристике Sphere Collider поставила галочку напротив функции Is Trigger
7) Для изменения цвета, я вначале создаю материал правой кнопкой мыши на окне Assets (create->Naterial), выбирая его настройки, в моем случае - красный цвет
8) Для применения данного материала, его нужно переместить (зажатой кнопкой мыши) в необходимый обьект поля иерархии, в моем случае это cube
9) Далее, для создания механики реакции на столконвение (для обьекта sphere), переходим в окно инспектора, выбрав нужную кнопку в самом низу :Add Component, нажимаем на неё, далее на new Script и вписываем название нового скрипта - СheckCollaider(без пробела), нажимаем Create and Add и видим, как в окне асекц появился наш файл скрипта
10) Открываем созданный файл для его дальнейшей редакции
11) Добавляем в код функцию OnTriggerEnter, которая будет отвечать за проверку столкновения, а также добавим внутрь функции вывод в консоль имя обьекта столкновения
12) Сохраняем скрипт и проверяем его работу путем запуска сцены и передвижения в ней обьектов
[Редактирование скриптa](https://github.com/umi0193/DA-in-GameDev-lab1/blob/main/%D0%A0%D0%B5%D0%B4%D0%B0%D0%BA%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%B0.jpg)
13) Для того чтобы обьекты столкнулись - необходимо им задать свойства физических обьектов. Для этого нажимаем на обьект, для которого это необходимо (куб), Add Component -> RidgidBody
14) В описании задаем Is Kinematic и убираем галочку напротив Use Gravity, чтобы куб не провалился под другой обьект 
15) Теперь можно запускать сцену и перетащив сферу к кубу наблюдать в окне Console сообщение о столкновении
16) [Проверка работы скрипта - вывод в консоль столкновения](https://github.com/umi0193/DA-in-GameDev-lab1/blob/main/%D0%9F%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0%20%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B%20%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%B0%20-%20%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4%20%D0%B2%20%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D1%8C%20%D1%81%D1%82%D0%BE%D0%BB%D0%BA%D0%BD%D0%BE%D0%B2%D0%B5%D0%BD%D0%B8%D1%8F.jpg)
17) Убедившись в работе скрипта, добавляем в него функцию OnTriggerExit для идентификации и вывода информации о завершении столкновения обьектов. Для удобства подписываем вывод.
18) Возвращаемся к сцене и проверяем работу, предварительно сохранив изменения в коде 
[Результат вывода обновленного скрипта](https://github.com/umi0193/DA-in-GameDev-lab1/blob/main/%D0%A0%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%D1%81%D1%86%D0%B5%D0%BD%D1%8B%20%D0%BF%D0%BE%D1%81%D0%BB%D0%B5%20%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%81%D0%BC%D0%B5%D0%BD%D1%8B%20%D1%86%D0%B2%D0%B5%D1%82%D0%B0%202.jpg)
20) Для добавления интерактива - создаем в скрипте строку изменения цвета столкнувшегося обьекта, а после разьединения - возвращение цвета обратно. Для этого в соответствующие функции заносим данные о том, какой компонент, а затем материал обьекта нам нужно изменить, указывая необходимое значение в конце: GetComponent<Renderer>().material.SetColor("_Color", Color.green); 
21) Проверяем работу измененного скрипта
[Работа сцены после добавления смены цвета 1](https://github.com/umi0193/DA-in-GameDev-lab1/blob/main/%D0%A0%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%D1%81%D1%86%D0%B5%D0%BD%D1%8B%20%D0%BF%D0%BE%D1%81%D0%BB%D0%B5%20%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%81%D0%BC%D0%B5%D0%BD%D1%8B%20%D1%86%D0%B2%D0%B5%D1%82%D0%B0%201.jpg)
[Работа сцены после добавления смены цвета 2](https://github.com/umi0193/DA-in-GameDev-lab1/blob/main/%D0%A0%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%D1%81%D1%86%D0%B5%D0%BD%D1%8B%20%D0%BF%D0%BE%D1%81%D0%BB%D0%B5%20%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%81%D0%BC%D0%B5%D0%BD%D1%8B%20%D1%86%D0%B2%D0%B5%D1%82%D0%B0%202.jpg)

Итоговый скрипт "CheckCollaider": 
```cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CheckCollaider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }

    private void OnTriggerEnter(Collider other) {
        Debug.Log("Произошло столкновение с " + other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.green);
    }

    private void OnTriggerExit(Collider other) {
         Debug.Log("Завершили столкновение с " + other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.red);
    }
}

```

## Задание 2
### Продемонстрировать на сцене в Unity следующее:
### 1) Что произойдёт с координатами объекта, если он перестанет быть дочерним?



### 2) Создать три различных примера работы компонента RigidBody.



## Задание 3
### Реализовать на сцене генерацию n кубиков. Число n вводится пользователем после старта сцены.



## Выводы



## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
